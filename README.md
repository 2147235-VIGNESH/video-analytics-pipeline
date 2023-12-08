# video-analytics-pipeline
building a real-time surveillance system that performs analytics on live camera streams.

Scenario: You are part of a team, building a real-time surveillance system that performs
analytics on live camera streams. The system needs to process video frames in real-time, apply
analytics, and store or transmit the results. You are tasked with developing a critical component
of this system.
Scope: The user might ask for the camera footage for a particular time period. Provided the
duration and timestamp, the application must provide the respective footage to the user. The
timestamp and the duration of the video will be given by the user.
Expected results: We expect the code base( .py), DB file, Json file, along with a output video
Task 1:
Write Python code for a real-time video analytics pipeline that performs the following tasks:
For any configurations related tasks create a python config file and must create a SQL
Database for storing information.
1. Video Stream Ingestion
Simulate the ingestion of a live video stream using Python. You can use libraries like
OpenCV to read video frames from a video file. Consider that as a live stream and
provide code to capture frames continuously from the source.
2. Frame Processing
Develop a function or class that takes each incoming video frame and performs the
following actions:
a. Frame by frame process and create a json object for each frame.
b. Extract relevant information from the processed frame. The json must contain the
following information:
i. camera_id
ii. frame_id
iii. geo_location
iv. image_path (write the frames as jpg image file)
C. Consider that the streaming is 25 FPS. Hence for every second write any one frame
as an image file and reuse that file for the rest 24 frames. Hence it is enough to write
only one frame per second as an image file.
D. Simultaneously while processing frames, all the frame information must be written in a
json file.
3. Batching
As mentioned earlier, the duration of the video file (in secs) will be mentioned in the
config file. Based on the duration value, perform batching of above processed frame’s
information. Create a dictionary for every batch that consists of following keys:
i. batch_id
ii. starting_frame_id
iii. ending_frame_id
iv. timestamp

Apply your own logic to perform batching of frames for the mentioned duration in config.
3. Data Storage
Use any SQL Database and create necessary tables and columns to store batch
information. Every batch information must be logged in the DB.
4. Error Handling and Logging
Implement error handling and logging mechanisms in your code to capture and handle
exceptions that may occur during frame processing, data storage, or transmission.
Ensure that the code logs relevant information for debugging.
5. Concurrency and Performance
To improve performance, modify your code to handle multiple camera streams
concurrently. Consider there are 2 live streams and enable concurrent processing of
those frames in the application. Explain how you ensure thread safety and avoid race
conditions.
6. Documentation and Comments
Ensure your code is well-documented with comments that explain the purpose and
functionality of key functions or classes. Prepare a detailed word document that explains
your application in a way a user can understand.
Task 2:
1. Write a user driven python program that accepts,

➢ TIMESTAMP
➢ DURATION OF THE VIDEO FILE from the user.
Based on the above information, iterate through the batch information in the Database. Create a
metadata out of it which will be helpful in gathering the frame information from the json file.
Once the necessary frames are gathered convert them to a mp4 file and present them to the
user.
2. Error Handling and Logging
Implement error handling and logging mechanisms in your code to capture and handle
exceptions that may occur during frame processing, data storage, or transmission. Ensure that
the code logs relevant information for debugging.
3. Documentation and Comments
Ensure your code is well-documented with comments that explain the purpose and functionality
of key functions or classes. Prepare a detailed word document that explains your application in
a way a user can understand.
