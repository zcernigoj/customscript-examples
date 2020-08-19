//VERSION=3

// This is an example of how to get the data for 2 different dates from one input dataset.
// This example contains:
// - a function which checks if the provided dates are the same day: sameDay()
// - a function which retrieves the index of the sample (from samples variable) for the requested date (from inputData variable): getDataIndexForDate()


function setup (){
  return {
    input: [
      {datasource: "s1grd", bands:["VV", "VH"], mosaicking: "ORBIT"},
      {datasource: "s2l2a", bands:["B03", "B04", "B08", "B11", "B12"], mosaicking: "ORBIT"}
     ],   
    output: [
      {id: "default", bands: 3, sampleType: SampleType.AUTO}
    ]
  };
}

function sameDay(d1, d2) {
  return d1.getFullYear() === d2.getFullYear() &&
    d1.getMonth() === d2.getMonth() &&
    d1.getDate() === d2.getDate();
}

function getDataIndexForDate(dataset, dateString){
  
  for(const scene of dataset.scenes){
    // throw new Error(scene.date + " | " + new Date(dateString))
    if(sameDay(scene.date, new Date(dateString))){
      return scene.idx;
    }
  }
  
  // You can throw an error or just return null (depending on what you want to do with that further on).
  throw new Error(JSON.stringify(dataset))
  // return null;
}

function evaluatePixel(samples, inputData, inputMetadata, customData, outputMetadata) {
  
  // get indices for the correct samples in samples variable
  // for the dates from inputData variable
  var indexS1_T1 = getDataIndexForDate(inputData.s1grd, '2020-07-07');
  var indexS1_T2 = getDataIndexForDate(inputData.s1grd, '2020-07-07');
  var indexS2L2A = getDataIndexForDate(inputData.s2l2a, '2020-07-07');
  
  if(!indexS1_T1 || !indexS1_T2 || !indexS2L2A){
    throw new Error("some dataset has no data on the selected date");
  }
  
  var s1_1 = samples.s1grd[indexS1_T1]; // Assigns S1 data from t1
  var s1_2 = samples.s1grd[indexS1_T2]; // Assigns S1 data from t2
  var s2_1 = samples.s2l2a[indexS2L2A]; // Assigns S2 data from t1
  
  // ... your code ...
}