# ObjectDetectionExperiments
Here are steps you can follow to run object detection on your own devices.

First:
Download either VMware workstation or Ubuntu to access their environment to reduce work load on your device. Key for VMware (https://gist.github.com/williamgh2019/cc2ad94cc18cb930a0aab42ed8d39e6f) 
Or, you can use a edge device, ex: Jetson Nano, Raspberry Pi.

Second:
Install and config Anaconda environment using following commands on your device:

conda update --all
conda install pytorch torchvision torchaudio cpuonly -c pytorch
pip install openmim
sudo apt install build-essential
sudo apt install libgl1-mesa-glx
conda install -c conda-forge opencv
mim install mmdet

(You might need an extra step before running the last command, the program might show you a warning or an error, this solution can be found online)

Third:
After you completed Second steps, you should find a mmdetection folder in your desktop. Open your command prompt, use "cd" to the directory and use "ls" to make sure that here conntains run.sh file and demo folder.
Save the image that you want to test and name it "demo.jpg" (of course it can be any name you want).

Go to this website to find models and configurations: https://github.com/open-mmlab/mmdetection/tree/master/configs

In my example, I used yolov3:https://github.com/open-mmlab/mmdetection/tree/master/configs/yolo

![图片](https://user-images.githubusercontent.com/71995520/180578488-e0f89c2f-3251-4e1b-bb47-d801046d10e6.png)

Down the model first, copy and paste it to your checkpoint folder. Now right click and rename the file, don't rename but copy the whole file name. This will replace "2" in my screenshot.  
Then, click Config, copy config name start from config.... This will replace "1" in my screenshot.

Now type "gedit run.sh" in command line to edit this file, it should be empty at this moment. We don't want every change in model and configuration to be made on command prompt, you know it will be a hassle.

Type these commands (from GitHub config and model name) in run.sh file
![图片](https://user-images.githubusercontent.com/71995520/180578872-12ecceba-e755-4209-9ad6-cf1f9ff801da.png)

Replace your chosen model and configuration as I mentioned in "1" and "2" position.

You are almost done! Control + S to save this file. (Note that I'm running command on my CPU, you can find tutorial here for other case: https://github.com/open-mmlab/mmdetection/blob/master/docs/en/get_started.md)

Last step:

Open another command prompt and type these:
![图片](https://user-images.githubusercontent.com/71995520/180579161-5c31db1c-8c1d-4920-a65d-fd895d792a3e.png)


You are all set!
