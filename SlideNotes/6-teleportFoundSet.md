# Teleporting a Found Set
Credit: [Wim Decorte, Soliant](https://www.soliantconsulting.com/blog/filemaker-teleportation-found-sets/)

## Demo
This technique allows you to "park" a found set that can be recalled later, without having to store complicated find requests or use snapshot links.

## Under the Hood 
Table Occurrences that share the same base table can be used for this technique. You need a layout based on a second table occurrence in order to "park" a found set on that layout. 

Using the Go To Related Records script step, select the table occurrence of your current layout and found set that you want to park. Then select the layout of the second, unrelated table occurrence to display the records. 

When this script step runs, it will park the found set on the second layout. Since it is not the same table occurrence, the parked found set is independent of the found set on the original layout. To restore the parked found set, just reverse the process from the parked found set on the second layout.