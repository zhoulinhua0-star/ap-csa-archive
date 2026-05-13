```java
// (a)
public boolean conflictsWith(Appointment other) {
    return this.getTime().overlapsWith(other.getTime());
}

// (b)
public void clearConflicts(Appointment appt) {
    for (int i = apptList.size() - 1; i >= 0; i--) {
        if ((Appointment)apptList.get(i).conflictsWith(appt)) {
            apptList.remove(i);
        }
    }
}

// (c)
public boolean addAppt(Appointment appt, boolean emergency) {
    if (emergency) {
        this.clearConflicts(appt);
        apptList.add(appt);
  } else {
        for (int i = apptList.size() - 1; i >= 0; i--) {
            if (!(Appointment)apptList.get(i).conflictsWith(appt)) { apptList.add(appt); }
            }
    }
    return apptList.contains(appt);
}

// OR:

public boolean addAppt(Appointment appt, boolean emergency) {
    if (emergency) {
        this.clearConflicts(appt);
    } else {
        for (int i = apptList.size() - 1; i >= 0; i--) {
            if ((Appointment)apptList.get(i).conflictsWith(appt)) { return false; }
        }
    }
    return apptList.add(appt);
}
```