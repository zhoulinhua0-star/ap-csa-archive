# Appointment

## Core Concept

- Composition

- better traversing the arraylist backwards when considering`list.remove(index)` method, so indices do not skip after deletes and it does avoid extra code.

## Time Complexity

- `conflictsWith(Appointment other)`: **O(1)**

- `clearConflicts(Appointment appt)`: **O(n^2)**, where `n^2` is `apptList.size()`

- `addAppt(Appointment appt, boolean emergency)`: **O(n^2)**