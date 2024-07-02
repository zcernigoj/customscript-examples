# parameters for `evaluatePixel()` function

* [first param (usually named `samples`)](#first-param-usually-named-samples)
    - [no datafusion, no multitemporal](#no-datafusion-no-multitemporal)
    - [datafusion, no multitemporal](#datafusion-no-multitemporal)
    - [no datafusion, multitemporal](#no-datafusion-multitemporal)
    - [datafusion, multitemporal](#datafusion-multitemporal)
* [second parameter (usually named `inputData`)](#second-parameter-usually-named-inputdata)
    - [no datafusion, no multitemporal](#no-datafusion-no-multitemporal-1)
    - [datafusion, no multitemporal](#datafusion-no-multitemporal-1)
    - [no datafusion, multitemporal](#no-datafusion-multitemporal-1)
    - [datafusion, multitemporal](#datafusion-multitemporal-1)


## first param (usually named `samples`)

#### no datafusion, no multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "B03": 0,
  "B04": 0,
  "dataMask": 0
}
```
</details>



#### datafusion, no multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "S2L2A": [
    {
      "B03": 0.0799,
      "B04": 0.0751,
      "B08": 0.0693,
      "B11": 0.0512,
      "B12": 0.041
    }
  ],
  "S1GRD": []
}
```
</details>

#### no datafusion, multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "B03": 0.2656,
  "B04": 0.2538,
  "dataMask": 1
}
```
</details>

#### datafusion, multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "S2L2A": [
    { // date in the first element of the second parameter (below) for this datasource (nameOfParam.S2L2A.scenes[0])
      "B03": 0.2656,
      "B04": 0.2538,
      "B08": 0.46490000000000004,
      "B11": 0.35850000000000004,
      "B12": 0.2866
    },
    { // date in the second element of the second parameter (below) for this datasource (nameOfParam.S2L2A.scenes[1])
      "B03": 0.5695,
      "B04": 0.5541,
      "B08": 0.6425000000000001,
      "B11": 0.5389,
      "B12": 0.5266000000000001
    },
    { // date in the third element of the second parameter (below) for this datasource (nameOfParam.S2L2A.scenes[2])
      "B03": 0.9767,
      "B04": 0.9152,
      "B08": 0.8883000000000001,
      "B11": 0.5063,
      "B12": 0.3537
    },
    {
      "B03": 0.0639,
      "B04": 0.0528,
      "B08": 0.3052,
      "B11": 0.1885,
      "B12": 0.1044
    },
    {
      "B03": 0.2647,
      "B04": 0.2452,
      "B08": 0.37620000000000003,
      "B11": 0.2439,
      "B12": 0.20750000000000002
    },
    {
      "B03": 0.1583,
      "B04": 0.1384,
      "B08": 0.3599,
      "B11": 0.22080000000000002,
      "B12": 0.1539
    },
    {
      "B03": 1.0521,
      "B04": 1.0647,
      "B08": 1.1304,
      "B11": 0.3561,
      "B12": 0.35950000000000004
    },
    {
      "B03": 0.158,
      "B04": 0.1494,
      "B08": 0.22260000000000002,
      "B11": 0.1761,
      "B12": 0.1501
    },
    {
      "B03": 0.058,
      "B04": 0.049300000000000004,
      "B08": 0.2651,
      "B11": 0.17600000000000002,
      "B12": 0.0944
    },
    {
      "B03": 0.1683,
      "B04": 0.1519,
      "B08": 0.34240000000000004,
      "B11": 0.2106,
      "B12": 0.1484
    },
    {
      "B03": 0.0606,
      "B04": 0.052000000000000005,
      "B08": 0.2725,
      "B11": 0.1829,
      "B12": 0.10690000000000001
    },
    {
      "B03": 0.5901000000000001,
      "B04": 0.5478000000000001,
      "B08": 0.5736,
      "B11": 0.2936,
      "B12": 0.2857
    },
    {
      "B03": 0.0644,
      "B04": 0.0557,
      "B08": 0.29910000000000003,
      "B11": 0.2033,
      "B12": 0.1136
    }
  ],
  "S1GRD": [
    { // date in the first element of the second parameter (below) for this datasource (nameOfParam.S1GRD.scenes[0])
      "VV": 0.09617745876312256,
      "VH": 0.030977655202150345
    },
    { // date in the second element of the second parameter (below) for this datasource (nameOfParam.S1GRD.scenes[1])
      "VV": 0.14343346655368805,
      "VH": 0.031039346009492874
    },
    { // date in the third element of the second parameter (below) for this datasource (nameOfParam.S1GRD.scenes[2])
      "VV": 0.1121753603219986,
      "VH": 0.02571764960885048
    },
    {
      "VV": 0.15628919005393982,
      "VH": 0.03164724260568619
    },
    {
      "VV": 0.1504020392894745,
      "VH": 0.034518156200647354
    },
    {
      "VV": 0.12250260263681412,
      "VH": 0.028507674112915993
    },
    {
      "VV": 0.12780514359474182,
      "VH": 0.02627670206129551
    },
    {
      "VV": 0.13227960467338562,
      "VH": 0.04269793629646301
    },
    {
      "VV": 0.11652147024869919,
      "VH": 0.03277454152703285
    }
  ]
}
```
</details>

## second parameter (usually named `inputData`)

#### no datafusion, no multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "idx": 0,
  "bandBuffers": [
    {},
    {},
    {}
  ]
}
```
</details>

#### datafusion, no multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "S2L2A": {
    "scenes": [],
    "normalizationFactor": 0.0001
  },
  "S1GRD": {
    "scenes": [],
    "normalizationFactor": 1
  }
}
```
</details>

#### no datafusion, multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "idx": 0,
  "bandBuffers": [
    {},
    {},
    {}
  ]
}
```
</details>

#### datafusion, multitemporal

<details>
  <summary>click to expand</summary>

```json
{
  "S2L2A": {
    "scenes": [
      {
        "date": "2021-02-19T00:00:00.000Z", // to get to this element: nameOfParam.S2L2A.scenes[0]
        "idx": 0,
        "bandBuffers": [
          {},
          {},
          {},
          {},
          {}
        ]
      },
      {
        "date": "2021-02-14T00:00:00.000Z", // to get to this element: nameOfParam.S2L2A.scenes[1]
        "idx": 1,
        "bandBuffers": [
          {},
          {},
          {},
          {},
          {}
        ]
      },
      {
        "date": "2021-02-09T00:00:00.000Z", // to get to this element: nameOfParam.S2L2A.scenes[2]
        "idx": 2,
        "bandBuffers": [
          {},
          {},
          {},
          {},
          {}
        ]
      },
      {
        "date": "2021-02-04T00:00:00.000Z",
        "idx": 3,
        "bandBuffers": [
          {},
          {},
          {},
          {},
          {}
        ]
      },
      {
        "date": "2021-01-30T00:00:00.000Z",
        "idx": 4,
        "bandBuffers": [
          {},
          {},
          {},
          {},
          {}
        ]
      },
      {
        "date": "2021-01-25T00:00:00.000Z",
        "idx": 5,
        "bandBuffers": [
          {},
          {},
          {},
          {},
          {}
        ]
      }
    ],
    "normalizationFactor": 0.0001
  },
  "S1GRD": {
    "scenes": [
      {
        "date": "2021-02-21T00:00:00.000Z", // to get to this element: nameOfParam.S1GRD.scenes[0]
        "idx": 0,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-20T00:00:00.000Z", // to get to this element: nameOfParam.S1GRD.scenes[1]
        "idx": 1,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-19T00:00:00.000Z", // to get to this element: nameOfParam.S1GRD.scenes[2]
        "idx": 2,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-15T00:00:00.000Z",
        "idx": 3,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-14T00:00:00.000Z",
        "idx": 4,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-09T00:00:00.000Z",
        "idx": 5,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-08T00:00:00.000Z",
        "idx": 6,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-07T00:00:00.000Z",
        "idx": 7,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-03T00:00:00.000Z",
        "idx": 8,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-02T00:00:00.000Z",
        "idx": 9,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-02-01T00:00:00.000Z",
        "idx": 10,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-01-28T00:00:00.000Z",
        "idx": 11,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-01-27T00:00:00.000Z",
        "idx": 12,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-01-26T00:00:00.000Z",
        "idx": 13,
        "bandBuffers": [
          {},
          {}
        ]
      },
      {
        "date": "2021-01-22T00:00:00.000Z",
        "idx": 14,
        "bandBuffers": [
          {},
          {}
        ]
      }
    ],
    "normalizationFactor": 1
  }
}
```
</details>
