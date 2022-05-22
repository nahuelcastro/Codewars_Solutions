## Formula 1 Race
---
You are a big fan of Formula 1.

There was a race last week-end, but ... you missed the live TV. You picked on the internet a list of the events during the race, and you want to get your champion's rank at the end of the race.

An event is a pilot ID followed by a type. There are two types of events:

-   'O' : a pilot is overtaking the one just in front of him
-   'I' : a pilot had an incident... and is forced to quit the race (and subsequently all pilots after this one gain one rank)

The list of events is passed as a string where events are separated with a space, first event first. *e.g: "2 O 12 I" means the pilot#2 overtook, then the pilot#12 had an incident.*

Your function will return the rank of your champion at the end of the race, given your champion's ID (as int) and the list of events. Return -1 if your champion had an incident.

NOTES:

-   there are 20 positions when the race starts (from 1 to 20, 1 being the one in front),
-   each pilot ID is his position when the races starts,
-   all events in entry lists are syntactically valid.

*Final tests contains about 20 fixed events, and 100 random tests with race length between 10 to 30 events. In the tests (fixed and random): the leading pilot never overtakes, and after having an incident, the pilot never appears in further events.*

Enjoy !

*Thanks to the Best french developer Contest 2019*

---

### Given Code


```python
def champion_rank(pilot: int, events: str) -> int:
    # your code here
    return -1
```

---

### Solution

```python

def champion_rank(pilot: int, events: str) -> int:
    pilot_by_position = {}
    position_by_pilot = {}
    q_positions = 20
    last_valid_position = q_positions
    events_list = events.split(" ")
    for i in range(1, q_positions + 1):
        pilot_by_position[i] = i
        position_by_pilot[i] = i

    i = 0
    while i < len(events_list) - 1:
        try:
            id = int(events_list[i])
            e = events_list[i + 1]

            if (e == 'I'):
                if position_by_pilot[id] != -1:
                    old_position = position_by_pilot[id]
                    position_by_pilot[id] = -1
                    for j in range(old_position + 1, last_valid_position + 1):
                        id_aux = pilot_by_position[j]
                        position_by_pilot[id_aux] -= 1
                        pos_aux = position_by_pilot[id_aux]
                        pilot_by_position[pos_aux] = id_aux
                    pilot_by_position[last_valid_position] = -1
                    last_valid_position -= 1
            elif (e == 'O'):
                if position_by_pilot[id] != -1 and position_by_pilot[id] != 1:
                    id_aux = pilot_by_position[position_by_pilot[id] - 1]
                    best_position = position_by_pilot[id] - 1
                    position_by_pilot[id] -= 1
                    position_by_pilot[id_aux] += 1

                    pilot_by_position[best_position] = id
                    pilot_by_position[best_position + 1] = id_aux
        except:
            print("Error")
            pass
        i += 2

    return position_by_pilot[pilot]
```


---


[See on CodeWars.com](https://www.codewars.com/kata/626d691649cb3c7acd63457b)