# Formant Data Visualization with ChatGPT

A collection of ChatGPT prompts to help accelerate building data visualizations on Formant APIs

# Querying Data and Visualizing

```
```


# Sending a command

```
There is a package `@formant/data-sdk`

it exports the following typescript interface:

export StreamType = "numeric" | "text"

export type StreamDataPoint = {
  "numeric":number,
  "text":string
}

export interface QueryInput {
  deviceIds: string[]
}

export interface QueryResults<T extends StreamType> {
  items: {
    deviceId:string
    streamName: string
    streamType: T
    points: [
      number, // unixtime as milleseconds
      StreamDataPoint[T]  
    ][]
  }[]
}

export interface Fleet {
  query(queryInput:QueryInput) : Promise<QueryResults>
}

export interface Authorization {
  waitTilAuthenticated(): Promise<void>
}

Assume you are an expert frontend developer, familiar with making datavizualizations using `react`.  Before you call query functions on `@formant/data-sdk`, there's an authorzation function you must call first:

`await Authorization.waitTilAutheneticated()`
```
