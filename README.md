# Identifying Agriculture Disease in Tomatoes

[Live demo](https://agriculture-disease-detection.onrender.com )

### Overview
Agriculture disease has proven to be a destructive force. The primary industry in the area that I grew up in is the greenhouse industry and a few years ago they saw just how devastating this issue can be. Affected plants need to be quarantined and early detection plays a significant role in this. It goes without saying that having the ability to detect agriculture disease is an important problem to solve.

### Solution
I decided to build a CNN in the hopes of being able to accurately identify specific diseases in tomatoes. Using a dataset of 10,000+ images of tomatoes and 20 labeled diseases I was able to achieve 90% with my classifier.

I have deployed a web app to demonstrate the functionality and I am also currently in the process of building a mobile app with ReactNative to see how effective the model is in a real-life setting.

### Process
I decided to build the CNN using the Fast.ai library. Fast.ai is a fantastic library, built on top of PyTorch and has a ton of useful built-in tools. One such tool is the learning rate finder, which allows us to easily find the optimal learning rate for a particular architecture and dataset. A few other really useful tools are one cycle learning and discriminative learning rates. I was first introduced to the Fast.ai library while completing Jeremy Howard's deep learning course and I have been experimenting with it ever since.

### Production
I started by saving my model to a pickle file and uploading to Google Drive. I then created a simple web app using the starlette framework. I packaged the app in a Docker image and deployed to a new hosting provider, Render. Render takes care of the CI process for you by using GitHub webhooks. All you have to do is push your code to GitHub and Render takes cares of deploying your app with your updates.

The web app consists of a simple client which allows users to upload images of tomatoes leaves and receive a prediction. The Predictions range from "healthy" to 19 other specific diseases. The client accesses the server-side model predictions through a designated endpoint.