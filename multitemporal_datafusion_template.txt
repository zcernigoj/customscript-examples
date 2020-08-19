//VERSION=3
// multitemporal by Harel Dan with data fusion
// ADVANCED

var setup = () => ({
  input: [
    {datasource: "s2l1c", bands:["B02", "B03", "B04", "B08", "B11"], units: "REFLECTANCE", mosaicking: "ORBIT"},
    {datasource: "s1grd", bands:["VV", "VH"], units: "REFLECTANCE", mosaicking: "ORBIT"},
    {datasource: "s2l2a", bands:["B02", "B03", "B04"], units: "REFLECTANCE", mosaicking: "ORBIT"}
  ],
  output: [
    { id: "default", bands: 3, sampleType: SampleType.AUTO }
  ],
})


function evaluatePixel(samples, inputData, inputMetadata, customData, outputMetadata) {
  /*
  For each processed pixel (each time the evaluatePixel is run), the parameters have the following structure
  samples:{
    "s2l2a":[
      {"B02": 123, "B03": 123, "B04": 123, ...},
      {"B02": 123, "B03": 123, "B04": 123, ...},
      // one for each date
    ],
    "s2l1c":[
      {"B02": 123, "B03": 123, "B04": 123, ...},
      {"B02": 123, "B03": 123, "B04": 123, ...},
      // one for each date
    ],
    "s1grd":[
      {"VV":123,"VH":123},
      {"VV":123,"VH":123},
      // one for each date
    ]
  },
  
  // CAUTION: THE DATES IN THE SCENES CAN DIFFER BETWEEN DATASETS
  // idx-es in the scenes of the dataset correspond to the indexes of the samples of that dataset (but not the other datasets)
  
  inputData:{
    "s2l2a":{
      "scenes":[
        {"date": "123", "idx": 0, ...]}
        {"date": "123", "idx": 1, ...]}
        // for each date one
      ],
      "normalizationFactor": 0.0001
    },
    "s2l1c":{
      "scenes":[
        {"date": "123", "idx": 0, ...]}
        {"date": "123", "idx": 1, ...]}
        // for each date one
      ],
      "normalizationFactor": 0.0001
    },
    "s1grd":{
      "scenes":[
        {"date": "123", "idx": 0, ...]}
        {"date": "123", "idx": 1, ...]}
        // for each date one
      ],
      "normalizationFactor": 0.0001
    },
  }
  
  inputMetadata, customData, outputMetadata: NOT IMPORTANT; NOT USED
  
  */
  
 // IF YOU NEED THE DATA (SAMPLES) FROM ALL DATASETS, HERE IS HOW TO ONLY USE THE DATA ON THE SAME DATES
 // Not dates from one dataset are in the other, so we need to filter the scenes and samples
 // plan: go through all the scenes of one dataset (since scenes have the dates and the indexes of the elements in the samples)
 // and find the scenes from other datasets on the same dates as for the selected dataset 
 // we also need to fix the arrays of samples
 
 // something like
 
 var S2L1CSamples = samples.s2l1c; // [{"B02": 123, "B03": 123, "B04": 123, ...}, {one for each date}],
 var S2L2ASamples = samples.s2l2a; // [{"B02": 123, "B03": 123, "B04": 123, ...}, {one for each date}],
 var S1Samples = samples.s1grd; // [{"VV": 123, "VH": 123, ...}, {one for each date}], 
  
 var S2L1CScenes = scenes.s2l1c.scenes;
 var S2L2AScenes = scenes.s2l2a.scenes;
 var S1Scenes = scenes.s1.scenes;
 
 var usableDates = []; // we can use only one variable since we are just interested in the dates
 var usableS2L1CSamples = [];
 var usableS2L2ASamples = [];
 var usableS1Samples = [];
 
 for(S2L1Cscene of S2L1CScenes){
    const date = S2L1Cscene.date;
    const S2L2Ascene = S2L2AScenes.find(scene => scene.date === date);
    const S1scene = S1Scenes.find(scene => scene.date === date);
    
    if(S2L2Ascene !== undefined && S1scene != undefined){
     usableDates.push(date);
     usableS2L1CSamples.push(S2L1CSamples[S2L1Cscene.idx]);
     usableS2L2ASamples.push(S2L2ASamples[S2L2Ascene.idx]);
     usableS1Samples.push(S1Samples[S1scene.idx]);
    }
 }
 
  // work with usableDates, usableS2L1CSamples, usableS2L2ASamples, usableS1Samples from here
 
 
}