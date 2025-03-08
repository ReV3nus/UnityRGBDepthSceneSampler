# Unity RGB and Depth Scene Sampler
This repository contains some utils to sample RGB and Depth images of custom scenes with editable methods. You can use it to sample your own custom virtual scenes to get datasets for training, such as 3DGS.

To use this, you can use `git clone https://github.com/ReV3nus/UnityRGBDepthSceneSampler.git` and move all the files to your own unity projects.

Currently supported for Built-in Render Pipeline(BiRP) and High Defination Render Pipeline(HDRP).

# How to use in BiRP 

You should create two GameObjects to sample the scene.

One of these could be an empty object. It acts as the sample center, so you should wether drag it in scene or modify its transform.

The other should be attached with RGBDSampler.cs. Here's what it looks like:

![image](https://github.com/user-attachments/assets/6472084c-a097-4ad4-8417-2b4c66aeb9c9)

For the **Sample File Settings** and **Camera Sample Params**, you can modify them freely as you want. Except the *sample center* should be the GameObject that mentioned above.

For the **Rendering Pipeline Settings**, you should set *Rppl* to *BiRP* and bind *BiRP Depth Material* to this projects' **Materials/BiRPDepthMaterial**.

After finished your settings, you can press **Capture Current View** to capture the RGB and Depth image of current camera view, or you can press **Manual Sample Scene** to sample your custom scene following methods defined in *ManualSampleScene()* Function of the script, which you can modify as well.

# How to use in HDRP

For the HDRP, most of the settings are in same way as BiRP. But the different thing is that you should create another GameObject and bind it into the **HDRP Depth Volume**.

To create the correct GameObject, you can first create an empty one. After that, add a **Custom Pass Volume** component to it and set it to this:
![image](https://github.com/user-attachments/assets/a42fca12-045d-4cc4-9f50-b46dc9264b48)

The *HDRPDepthMaterial* in above is also included in the *Material* Folder.

# Other things

Currently, I haven't implemented it in Universal Render Pipeline(URP). This might be a future work.


