---
title: "Surface Vehicle - Cross Track Error"
excerpt: "Calculation of cross track error"

categories:
  - Surface Vehicle
tags:
  - Navigation, Cross Track Error
last_modified_at: 2021-05-25T17:00:00-05:00
---



## 1. Check Whether Ownship is at the Leftside

- 

```python
import numpy as np

def is_os_leftside(wp_x_past, wp_y_past, wp_x_goal, wp_y_goal, eta_os):
    """
    If ownship is at the leftside of a line connecting wp_goal and wp_past
    return 1
    otherwise -1
    - eta_os = np.array()
    """
    x_os = eta_os[0][0]
    y_os = eta_os[1][0]
    
    is_left = -1    # (False)

    if ((wp_x_goal - wp_x_past) * (y_os - wp_y_past) - (wp_y_goal - wp_y_past) * (x_os - wp_x_past)) > 0:
        is_left = 1     # (True)
    else:
        pass
    return is_left
  
# Test code
if __name__ == '__main__':
    """
    Test "is_os_leftside"
    """
    eta_os = np.array([[0.0],
                       [0.0],
                       [0.0]])
    print(is_os_leftside(wp_x_past=-0.5, wp_y_past=0.0, wp_x_goal=1.0, wp_y_goal=1.0, eta_os=eta_os))
```



## 2. Angle between Two Lines for Given Three points

- 

```python
def ang_three_pt(wp_x_past, wp_y_past, wp_x_goal, wp_y_goal, eta_os):
    """
    Calculate an angle formed by two lines for given three points (wp_past, wp_goal, eta_os)
    - eta_os = np.array()
    """
    x_os = eta_os[0][0]
    y_os = eta_os[1][0]

    a = np.hypot(wp_x_goal - wp_x_past, wp_y_goal - wp_y_past)
    b = np.hypot(x_os - wp_x_past, y_os - wp_y_past)

    ang = np.arccos(((wp_x_goal - wp_x_past) * (x_os - wp_x_past) + (wp_y_goal - wp_y_past) * (y_os - wp_y_past)) / (a * b))
    if b == 0:
        ang = 0
    else:
        pass

    return ang

# Test
if __name__ == '__main__':
    """
    #. Test "ang_three_pt"
    """
    eta_os = np.array([[0.0],
                       [0.0],
                       [0.0]])
    print(ang_three_pt(wp_x_past=-0.5, wp_y_past=0.0, wp_x_goal=1.0, wp_y_goal=1.0, eta_os=eta_os))
```



## 3. Cross Track Error (Distance Off Course)

- Two funtions `is_os_leftside()` and `ang_three_pt()` is required to run the following function 

```python
import numpy as np

def xtk(wp_x_past, wp_y_past, wp_x_goal, wp_y_goal, eta_os):
    """
    Calculate cross track error (distance off course)
    """
    x_os = eta_os[0][0]
    y_os = eta_os[1][0]

    # Angle between two lines for given three points (wp_past, wp_goal, eta_os)
    theta = ang_three_pt(wp_x_past, wp_y_past, wp_x_goal, wp_y_goal, eta_os)
    # Distance between 'eta_os' to 'wp_goal'
    rho = np.hypot(wp_x_goal - x_os, wp_y_goal - y_os)
    # Is ownship positioned at the leftside of the course?
    is_left = is_os_leftside(wp_x_past, wp_y_past, wp_x_goal, wp_y_goal, eta_os)

    # Cross track error
    error = -is_left * rho * np.sin(theta)

    return error
  
if __name__ == '__main__':
		"""
    #. Test "xtk"
    """
    eta_os = np.array([[0.5],
                       [-0.5],
                       [0.0]])

    print(xtk(wp_x_past=-1.0, wp_y_past=-1.0, wp_x_goal=1.0, wp_y_goal=1.0, eta_os=eta_os))
```



## References

- 

