```java
// (a)
public Reservation requestRoom(String guestName) {
    for (int i = 0; i < rooms.length; i++) {
        if (rooms[i].getRoomNumber() == null) {
            return new Reservation(guestName, rooms[i].getRoomNumber());
           }
    }
    waitList.add(guestName);
    return null;
}

// (b)
public Reservation cancelAndReassign(Reservation res) {
    rooms[res.getRoomNumber()] = null;
    if (!waitList.isEmpty()) {
         waitList.remove(0);
         return new Reservation((String)waitList.get(0), res.getRoomNumber());
    } else {
         return null;
    }
}
```