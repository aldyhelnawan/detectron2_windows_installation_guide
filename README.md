# detectron2_windows_installation_guide

My method to install detectron2 for Windows 10 with Anaconda (April 9th 2022)

Here's the env file consist of 2 types of pytorch, the gpu (that CUDA enable), and the cpu only.

The first thing to do is to clone the [detectron2 repository](https://github.com/facebookresearch/detectron2):

    git clone https://github.com/facebookresearch/detectron2.git

And the requirements for Windows 10:
1. Ninja for Windows (For reference see [Ninja Build Website](https://ninja-build.org/))
2. Install [MinGW 64-bit](https://sourceforge.net/projects/mingw/) (CygWin is also ok)
3. Install Visual Code Studio 2019
4. Install Nvidia CUDA 11.0 (Or check the recommended version from the [guide](https://pytorch.org/))

The requirements for your python environment using anaconda:
1. Python 3.8 
2. Install pytorch for cuda >=11.0 (for reference see [Pytorch Website](https://pytorch.org/)). Example:
   
       conda install pytorch torchvision torchaudio cudatoolkit=11.0 -c pytorch
  
3. Install Cython

       pip install cython
    or
    
       conda install -c anaconda cython
    
5. Install OpenCV

       pip install opencv-python

6. Install Pywin32

       pip install pywin32
        
    or
    
       conda install -c conda-forge pywin32

7. Install pycocotools

       pip install "git+https://github.com/philferriere/cocoapi.git#egg=pycocotools&subdirectory=PythonAPI"

8. Install git (if git doesn't detected on your cmd)
   
       conda install -c anaconda git
   
For the steps, install these dependencies before install detectron2 to your python environment.
For instaling detectron2 see [here](https://github.com/facebookresearch/detectron2)

## Optional
Despite of manually install the anaconda environment for installing detectron2, here's the anaconda env (.yaml) file you can use.
After import the venv, the next step you need to do is setup the detectron2:
* Set the distutils

      SET DISTUTILS_USE_SDK=1
    
* Call the __vcvars64.bat__ file to your cmd window:

      call "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"
      
* Go to the detectron2 folder, and insert this command:

      python setup.py build develop
   
* Then, you can check the installation by check pytorch and detectron2 (See the official guide [here1](https://detectron2.readthedocs.io/en/latest/tutorials/install.html) 
or [here2](https://detectron2.readthedocs.io/en/latest/tutorials/getting_started.html) to confirm the installation).

## Reference:
__Detectron2__

@misc{wu2019detectron2,
  author =       {Yuxin Wu and Alexander Kirillov and Francisco Massa and
                  Wan-Yen Lo and Ross Girshick},
  title =        {Detectron2},
  howpublished = {\url{https://github.com/facebookresearch/detectron2}},
  year =         {2019}
}

__Pytorch__

https://pytorch.org/

__Pytorch Forum__

[Solution by RujunLong's comment](https://discuss.pytorch.org/t/detectron-2-on-windows-10/93639/3)

__AugmentedStartups__

Got some solution from this [video](https://youtu.be/JC4D9kfZdDI) by AugmentedStartups

__Github Detectron2 Issue#9__

You can see for other solutions [here](https://github.com/facebookresearch/detectron2/issues/9)
