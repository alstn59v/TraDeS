# Track to Detect and Segment: An Online Multi-Object Tracker (CVPR 2021)

## Original Repository

* JialianW/TraDeS [GitHub](https://github.com/JialianW/TraDeS)

# Installation


The code was tested with [Anaconda](https://www.anaconda.com/download) Python 3.9.12, CUDA 11.7, and [PyTorch]((http://pytorch.org/)) v1.12.1.
Check your gcc version by 'gcc -v'. gcc version may need to be higher than v4.8 in order to compile the DCNv2 package. I tested the code with both gcc v9.4.0.
After installing Anaconda:

0. [Optional but highly recommended] create a new conda environment.

    ~~~
    conda create --name trades
    ~~~
    And activate the environment.

    ~~~
    conda activate trades
    ~~~

1. Install PyTorch:

    ~~~
    conda install pytorch torchvision cudatoolkit -c pytorch
    ~~~


2. Install COCOAPI:

    ~~~
    pip install cython; pip install -U 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'
    ~~~

3. Clone this repo:

    ~~~
    git clone https://github.com/alstn59v/TraDeS.git
    ~~~

4. Install the requirements

    ~~~
    cd $TraDeS_ROOT
    pip install -r requirements.txt
    ~~~

5. Build nms

    ~~~
    cd $TraDeS_ROOT/src/lib/external
    python setup.py build_ext --inplace
    ~~~

6. Compile deformable convolutional (Successuflly compiled with both gcc v5.4.0 and v8.4.0. gcc version should be higher than v4.8).

    ~~~
    cd $TraDeS_ROOT/src/lib/model/networks/DCNv2
    python setup.py build develop
    ~~~
   (modified from [DCNv2](https://github.com/CharlesShang/DCNv2/) and [DCNv2_latest](https://github.com/jinfagang/DCNv2_latest/))

7. Create subprocess_TraDeS.py .

   ~~~
   1) Duplicate subprocess.py and rename(subprocess_TraDeS.py).
       subprocess.py path: $Your_anaconda_ROOT/envs/lib/python3.9/subprocess.py
   2) Modify subprocess_TraDeS.py.
       "~, check=True, ~" to "~, check=False, ~"
   ~~~

## Acknowledgment
Many thanks to [TraDeS](https://github.com/JialianW/TraDeS) authors for their great framework!

Many thanks to [Issue Comment in CenterTrack](https://github.com/xingyizhou/CenterTrack/issues/98#issuecomment-783209427) comment author issue solving!

Many thanks to [DCNv2_last](https://github.com/jinfagang/DCNv2_latest) authors for their great framework!

Many thanks to [TrackEval](https://github.com/JonathonLuiten/TrackEval) authors for their great tool!
