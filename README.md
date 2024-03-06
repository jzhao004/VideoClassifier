## Demonstration Android app to showcase a video classification model operating in real time 

<img src="https://github.com/jzhao004/VideoClassifierApp/assets/33961266/96cb6797-504d-405a-ac92-b9ac91225a80" height="360">

### Getting started 
- Add model file: Place the model.pt file into the VideoClassifierApp/app/src/main/assets folder

### Usage 

#### Step 1: Upload video or image(s) 
- Begin by uploading a video or specific frame(s) from a video that you wish to classify

#### Step 2: Frame extraction (for videos)
- If a video is uploaded, the application will automatically extract 8 frames evenly distributed throughout the video's duration

#### Step 3: Classification
- The model will classify each extracted frame or uploaded image separately

#### Step 4: Aggregation of results 
- Finally, the results from each frame/image are aggregated to determine the overall classification of the video or image set

#### Step 5: Output of results
 The application provides the following output:
 
- Overall classification of the video or image set
- Classification of each frame extracted or image uploaded
- Number of frames extracted or images uploaded
- Time taken for classification 

If a video is uploaded, additional information is provided:

- Dimension of the video
- Duration of the video 
- Time taken for frame extraction
