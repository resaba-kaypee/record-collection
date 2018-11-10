# record-collection
var collection = {
    "2548": { //collection[0]
      "album": "Slippery When Wet",
      "artist": "Bon Jovi",
      "tracks": [ 
        "Let It Rock", 
        "You Give Love a Bad Name" 
      ]
    },
    "2468": { // collection[1] property (id)
      "album": "1999", // 2468[0]property(prop)
      "artist": "Prince", // 2468[1]property(prop)
      "tracks": [  //property (prop)
        "1999", // tracks[0](value)
        "Little Red Corvette" //tracks[1](value) 
      ]
    },
    "1245": { //collection [2]
      "artist": "Robert Palmer",
      "tracks": [ ]
    },
    "5439": { //collection [3]
      "album": "ABBA Gold"
    }
};
// Keep a copy of the collection for tests
var collectionCopy = JSON.parse(JSON.stringify(collection));

// Only change code below this line
function updateRecords(id, prop, value) {

if(prop !== "tracks" && value !== ""){
  collection[id][prop] = value;
} else if (prop === "tracks" && !collection[id].hasOwnProperty("tracks")) {
  collection[id].tracks = [];
  collection[id].tracks.push(value)
} else if (prop === "tracks" && value !== ""){
  collection[id][prop].push(value)
} else {
  if(value === "") {
    delete collection[id][prop];
  }
}
  return collection;
}

// Alter values below to test your code
console.log(updateRecords(5439, "artist", "ABBA"));
