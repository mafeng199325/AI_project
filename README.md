# 借鉴恩培老师的代码进行学习
这个仓库的代码是验证rk3588板子烧录之后，直接运行代码查看功能是否正常。
```
# 编译程序
cmake -S . -B build
cmake --build build 

# 运行测试命令
./build/mobilenet ./weights/mobilenet_v1.rknn ./images/dog_224x224.jpg 

# 如果正确运行，你会看到如下输出：
model input num: 1, output num: 1
input tensors:
  index=0, name=input, n_dims=4, dims=[1, 224, 224, 3], n_elems=150528, size=150528, fmt=NHWC, type=INT8, qnt_type=AFFINE, zp=0, scale=0.007812
output tensors:
  index=0, name=MobilenetV1/Predictions/Reshape_1, n_dims=2, dims=[1, 1001, 0, 0], n_elems=1001, size=1001, fmt=UNDEFINED, type=INT8, qnt_type=AFFINE, zp=-128, scale=0.003906
rknn_run
 --- Top5 ---
156: 0.984375
155: 0.007812
205: 0.003906
 -1: 0.000000
 -1: 0.000000
