# "JSON-ify" Your Data
Credit: [Kevin Frank, FileMaker Hacks](https://filemakerhacks.com/2021/12/27/connecting-portals-to-json-arrays/)

## Demo
This demo presents a model where portals are "connected" to an underlying JSON array of object data for storage. Manipulating the portal will result in instant updates of the JSON Storage.

This technique has a lot of applications, but most importantly allows for "virtual portals" with no need for database schema to present and edit data. 

## Under the Hood
A hybrid of script triggers, virtual lists and found set portals. Virtual lists can be used to display data calculated from a JSON array. Triggers can be used to push and pull information.