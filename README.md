<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

</head>
<body>

<h1>YOLOv4 Object Detection with Darknet</h1>

<p>This repository demonstrates how to set up and run <strong>YOLOv4</strong> for object detection using the <strong>Darknet</strong> framework. With GPU and OpenCV enabled, this setup accelerates object detection on images.</p>

<h2>Features</h2>
<ul>
  <li>Build Darknet with <strong>GPU</strong>, <strong>CUDNN</strong>, and <strong>OpenCV</strong> support.</li>
  <li>Download and run pre-trained YOLOv4 weights.</li>
  <li>Upload custom images and perform object detection.</li>
  <li>Display results using OpenCV.</li>
</ul>

<h2>Installation</h2>
<ol>
  <li>Clone the Darknet repository:</li>
  <pre><code>!git clone https://github.com/AlexeyAB/darknet</code></pre>

  <li>Enable GPU and OpenCV in the Makefile:</li>
  <pre><code>
!sed -i 's/OPENCV=0/OPENCV=1/' Makefile
!sed -i 's/GPU=0/GPU=1/' Makefile
!sed -i 's/CUDNN=0/CUDNN=1/' Makefile
!sed -i 's/CUDNN_HALF=0/CUDNN_HALF=1/' Makefile
  </code></pre>

  <li>Build Darknet:</li>
  <pre><code>!make</code></pre>

  <li>Download YOLOv4 weights:</li>
  <pre><code>!wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights</code></pre>

</ol>

<h2>Usage</h2>
<ol>
  <li>Run object detection on the provided test image:</li>
  <pre><code>!./darknet detector test cfg/coco.data cfg/yolov4.cfg yolov4.weights data/person.jpg</code></pre>

  <li>Display the results:</li>
  <pre><code>imShow('predictions.jpg')</code></pre>

  <li>Upload a custom image for detection:</li>
  <pre><code>
upload()
!./darknet detector test cfg/coco.data cfg/yolov4.cfg yolov4.weights ../YourImage.jpg
imShow('predictions.jpg')
  </code></pre>
</ol>

<h2>Credits</h2>
<p>Darknet framework: <a href="https://github.com/AlexeyAB/darknet">AlexeyAB Darknet</a></p>

</body>
</html>
