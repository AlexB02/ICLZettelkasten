### Definition
An [[Abstract Data Type]] in [[Java]] containing information about a date.

### Representations
- seconds from 1970
- [[Tuple]] of day, month, year

### [[Contract]]
- values must be all past, present and future dates
- Must be possible to perform the following:
  - construct a date from year, month & day
  - compare dates
  - render a date in ISO format
  - advance a day by n days

```java
public Date(final int y, final int m, final int d);
public int compareTo(final Date that);
public String toString() {};
public void advance(final int n);
```

#C40009 