# record-collection
var collection = {
    "2548": {                                   //collection
      "album": "Slippery When Wet",
      "artist": "Bon Jovi",
      "tracks": [ 
        "Let It Rock", 
        "You Give Love a Bad Name" 
      ]
    },
    "2468": {                                   // collection property (id)
      "album": "1999",                          // 2468[0]property(prop)
      "artist": "Prince",                       // 2468[1]property(prop)
      "tracks": [                               // property (prop)
        "1999",                                 // tracks[0](value)
        "Little Red Corvette"                   // tracks[1](value) 
      ]
    },
    "1245": {                                   // collection
      "artist": "Robert Palmer",
      "tracks": [ ]
    },
    "5439": {                                   //collection
      "album": "ABBA Gold"
    }
};
// Keep a copy of the collection for tests
var collectionCopy = JSON.parse(JSON.stringify(collection));

// Only change code below this line
function updateRecords(id, prop, value) {
    // If prop isn't "tracks" and value isn't empty (""), update or set the value for that record album's property.
if(prop !== "tracks" && value !== ""){
  collection[id][prop] = value;
    // If prop is "tracks" but the album doesn't have a "tracks" property, create an empty array before adding the new value to the album's corresponding property.
} else if (prop === "tracks" && !collection[id].hasOwnProperty("tracks")) {
  collection[id].tracks = [];
  collection[id].tracks.push(value)
    // If prop is "tracks" and value isn't empty (""), push the value onto the end of the album's existing tracks array.
} else if (prop === "tracks" && value !== ""){
  collection[id][prop].push(value)
  // If value is empty (""), delete the given prop property from the album.
} else {
  if(value === "") {
    delete collection[id][prop];
  }
}
  return collection;
}

// Alter values below to test your code
console.log(updateRecords(5439, "artist", "ABBA"));
