# Hello-Bot AI Project

## Object Detection
<img src='https://github.com/ultralytics/docs/releases/download/0/object-detection-examples.avif'>

Object detection is a task that involves identifying the location and class of objects in an image or video stream.

The output of an object detector is a set of bounding boxes that enclose the objects in the image, along with class labels and confidence scores for each box. Object detection is a good choice when you need to identify objects of interest in a scene, but don't need to know exactly where the object is or its exact shape.

## yolov8n openvino model 을 이용하여 Hello Bot AI 프로젝트 개발
we cover exporting YOLOv8 models to the OpenVINO format
OpenVINO, short for Open Visual Inference & Neural Network Optimization toolkit, is a comprehensive toolkit for optimizing and deploying AI inference models. Even though the name contains Visual, OpenVINO also supports various additional tasks including language, audio, time series, etc.

Benefits of OpenVINO
Performance: OpenVINO delivers high-performance inference by utilizing the power of Intel CPUs, integrated and discrete GPUs, and FPGAs.
Support for Heterogeneous Execution: OpenVINO provides an API to write once and deploy on any supported Intel hardware (CPU, GPU, FPGA, VPU, etc.).
Model Optimizer: OpenVINO provides a Model Optimizer that imports, converts, and optimizes models from popular deep learning frameworks such as PyTorch, TensorFlow, TensorFlow Lite, Keras, ONNX, PaddlePaddle, and Caffe.
Ease of Use: The toolkit comes with more than 80 tutorial notebooks (including YOLOv8 optimization) teaching different aspects of the toolkit.
OpenVINO Export Structure
When you export a model to OpenVINO format, it results in a directory containing the following:

XML file: Describes the network topology.
BIN file: Contains the weights and biases binary data.
Mapping file: Holds mapping of original model output tensors to OpenVINO tensor names.
You can use these files to run inference with the OpenVINO Inference Engine.

Using OpenVINO Export in Deployment
Once you have the OpenVINO files, you can use the OpenVINO Runtime to run the model. The Runtime provides a unified API to inference across all supported Intel hardware. It also provides advanced capabilities like load balancing across Intel hardware and asynchronous execution. For more information on running the inference, refer to the Inference with OpenVINO Runtime Guide.

Remember, you'll need the XML and BIN files as well as any application-specific settings like input size, scale factor for normalization, etc., to correctly set up and use the model with the Runtime.

In your deployment application, you would typically do the following steps:

Initialize OpenVINO by creating core = Core().
Load the model using the core.read_model() method.
Compile the model using the core.compile_model() function.
Prepare the input (image, text, audio, etc.).
Run inference using compiled_model(input_data).
For more detailed steps and code snippets, refer to the OpenVINO documentation or API tutorial.
