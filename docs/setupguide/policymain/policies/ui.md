# Policies for User Interface and Interaction

This section defines policies that control the behavior and visibility of user interface elements within Smart DevOps. 

These policies help customize how users interact with the system by enabling or restricting certain UI features and views, ensuring a more focused and efficient user experience.

## **Show Complete Issues Policy**

This policy controls the visibility of issues based on their completion status.

| `polcod`                  | `polvar` | `polval` | `rtnum1` |
|---------------------------|----------|----------|----------|
| USR-OSSI-VERSION-CONTROL | SETUP    | SHOW-COMPLETE-ISSUES  | 1        |

  - `rtnum1 = 1` → Policy is **enabled** (ON)
  - `rtnum1 = 0` → Policy is **disabled** (OFF)

When enabled, the system displays all issues, including Complete (C), Active (A), and Inactive issues (C). 

This provides a full view of all items regardless of their current state.

## **Create Rollout Auto Flag Policy**

This policy controls the display and behavior of the rollout creation option in the interface.

| `polcod`                  | `polvar` | `polval` | `rtnum1` |
|---------------------------|----------|----------|----------|
| USR-OSSI-VERSION-CONTROL | SETUP    | CREATE-ROLLOUT-AUTO-FLAG  | 1        |

When enabled, a toggle button appears next to the Create Rollout option, allowing users to select Yes or No to initiate rollout creation.

---