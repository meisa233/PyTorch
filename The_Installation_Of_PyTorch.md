### 1.查看cuda版本
来源：https://zhuanlan.zhihu.com/p/48641682<br />
```
cat /usr/lib/cuda/version.txt
# 有的电脑是/usr/local/cuda/version.txt
```
但是有人吐槽上面这种方法不准<br />

另外一种方法
```
nvcc --version
```
如果nvcc没有安装<br />
输入以下命令
```
sudo apt install nvidia-cuda-toolkit
```
### 2.找到合适的PyTorch的安装轮子
安装方法来自：<br />
https://blog.csdn.net/finviento/article/details/80835044<br />
>
理论上可以直接输入命令安装，但是我发现我租的这个服务器是cuda 9.1，没有办法直接安装，但是官网上提供了可用的轮子<br />
https://pytorch.org/get-started/previous-versions/<br />
搜索“cu91”,在电脑上使用pip install url地址命令安装即可<br />
但是，注意安装的时候可能会报错MemorryError<br />
于是，采用以下命令<br />
```
sudo pip --no-cache-dir install https://download.pytorch.org/whl/cu91/torch-0.4.0-cp27-cp27mu-linux_x86_64.whl
```
然后安装torchvision
```
sudo pip install torchvision
```
