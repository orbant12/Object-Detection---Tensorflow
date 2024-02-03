# Tensorflow Object Detection Walkthrough

<h3>Let's Go Through my Demo Process To Detect Anything </h3>
    
<b>1.) Step: </b> Pick The Object --> He is Kope my dog
<pre>
    <img src="https://github.com/orbant12/Object-Detection---Tensorflow/assets/124793231/f057196b-a864-47b9-ad92-f72fb039bf34" style="width:200px"  />
</pre>

---

<b>2.) Step: </b> Capture Images for Training and Testing --> Web Cam Needed !
<b>Note:</b> If you want the model to detect a more `general label` you will need about `100-200` images with different shapes and angles. </br>
For a `specific object` <span style="opacity:0.5">( Like --> Detect my dog )</span> you will need about `10-20` images with the same object from different angles.
<h6>· Python Script Generates all Folders Required for Storage --> Tensorflow/workspace/images/collectedimages</h6>
<pre>
<img src="https://github.com/orbant12/Object-Detection---Tensorflow/assets/124793231/eb0e73ce-5eb8-4db4-bd7f-93f7e6634708" style="width:600px" />
</pre>

---


<b>3.) Step: </b> Label Images --> `xml` file 
<h6>· Split All Units with 80% to Train Folder - 20% to Test Folder - 1 unit: { Photo + XML } </h6>
<h6>· Folders Created by Script in [ Tensorflow/workspace/images/test or train]  </h6>
<pre>
<img src="https://github.com/orbant12/Object-Detection---Tensorflow/assets/124793231/0a88bdf7-bf03-4883-a4e5-94532b291a49" style="width:800px" />
</pre>

---

<h1 align="center">Results</h1>

https://github.com/orbant12/Object-Detection---Tensorflow/assets/124793231/ebc373da-cb67-4a7d-8c18-01f665252281



https://github.com/orbant12/Object-Detection---Tensorflow/assets/124793231/893b1b3a-2c2a-4a5d-85ce-cac0d0b40458


---

# Setup Steps
<br />
<b>Step 1.</b> Clone this repository: https://github.com/orbant12/Object-Detection---Tensorflow.git
<br/><br/>
<b>Step 2.</b> Create a new virtual environment 
<pre>
python -m venv od-venv
</pre> 
<br/>
<b>Step 3.</b> Activate your virtual environment
<pre>
source tfod/bin/activate # Linux
.\od-venv\Scripts\activate # Windows 
</pre>
<br/>
<b>Step 4.</b> Install dependencies and add virtual environment to the Python Kernel
<pre>
python -m pip install --upgrade pip
pip install ipykernel
python -m ipykernel install --user --name=od-venv
</pre>
<br/>
<b>Step 5.</b> Collect images using the Notebook
<pre>
<a href="https://github.com/orbant12/Object-Detection---Tensorflow/blob/master/1.%20Image%20Collection.ipynb">1. Image Collection.ipynb</a> - ensure you change the kernel to the virtual environment as shown below
</pre>
<br/>
<b>Step 6.</b> Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders. <br/>
<pre>
    \ObjectDetect\Tensorflow\workspace\images\train<br />
    \ObjectDetect\Tensorflow\workspace\images\test
</pre>
<br/><br/>
<b>Step 7.</b> Begin training process by opening <a href="https://github.com/orbant12/Object-Detection---Tensorflow/blob/master/2.%20Training%20and%20Detection.ipynb">2. Training and Detection.ipynb</a>, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 
<br /><br/>
<b>Step 8.</b> During this process the Notebook will install Tensorflow Object Detection. You should ideally receive a notification indicating that the API has installed successfully at Step 8 with the last line stating OK.
<pre>
<img src="https://github.com/orbant12/Object-Detection---Tensorflow/assets/124793231/ef8c6e2f-00f6-4a09-b302-dabbbcbe1c1d">
</pre>
If not, resolve installation errors by referring to the <a href="https://github.com/orbant12/Object-Detection---Tensorflow/blob/master/Error%20Guide.md">Error Guide.md</a> in this folder.
<br /> <br/>
<b>Final Step: </b> Once you get to step 6. Train the model, inside of the notebook, you may choose to train the model from cmd within the virtual enviroment for live loss metrics.
<br />

---

<b>Optional Step: </b> You can optionally evaluate your model inside of Tensorboard. Once the model has been trained and you have run the evaluation command under Step 7. Navigate to the evaluation folder for your trained model e.g. 
<pre> cd Tensorlfow/workspace/models/my_ssd_mobnet/eval</pre> 
and open Tensorboard with the following command
<pre>tensorboard --logdir=. </pre>
Tensorboard will be accessible through your browser and you will be able to see metrics including mAP - mean Average Precision, and Recall.
<br />
