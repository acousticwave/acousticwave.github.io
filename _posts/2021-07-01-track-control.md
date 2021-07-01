---
title: "Track Control"
excerpt: "Track Control methods for Surface Vehicles"

categories:
  - Env
tags:
  - Env
last_modified_at: 2021-07-01T22:00:00-05:00
---



## Track Control



### 1. Wheel Over Position

- Several factors affect to a turn of a surface vehicle.
- A surface vehicle cannot make a immediate turn.
- WOP (Wheel over position) is usually considered to make a turn for cource change

{% include figure image_path="/assets/images/2021-07-01-track-control-wop.png" alt="this is a wop image" caption=" " %}

```python
  def wheel_over_dist(wp_past, wp_goal, wp_next_goal, wp_i, wp_i_max, R=10, F=5, eps_init=3, eps_max=20):

    """
    This calculates 'eps', wheel over distance,
    for updating waypoint considering the turning radius and change of course angle

    - {wp_past, wp_goal, wp_next_goal}: waypoinsts to be used for calculation of theta
    - eps = F + R * sin(theta/2), where
      
      F = one ship's length          [m]
      w = rate of turn,              [Rad.]
      R = Radius of turn, and        [m]
      theta = change of course angle [Rad.]
    """

    if wp_i == wp_i_max:
        eps = eps_init    # If current 'wp_goal' is the last waypoint
        
    else:
        theta = np.pi - ang_three_pt2(wp_past, wp_goal, wp_next_goal)  # [Rad]
        eps = F + R * np.sin(theta / 2)
        eps = np.clip(eps, F, eps_max)   # Clipping

    return eps
```

