# Tools
操作过程：
1. 先使用Blender/export_poses.py从blender软件中提取相机位姿的轨迹真值, 生成camera_transforms.txt
2. 使用Replica/Blender2Replica.py将上一步提取到的相机位姿转换成Replcia_SDK渲染器需要的processed_poses.txt（(c2w−1)T）, 以及Replica数据集的轨迹真值文件traj.txt（c2w）。
3. 使用Replica_SDK渲染器，读取processed_poses.txt进行渲染，得到RGB-D图像。
此步骤参考
```
cd ~/ImageSave/office0_loop
~/Replica-Dataset/build/ReplicaSDK/ReplicaRenderer ~/RawMaterial/office_0/mesh.ply  ~/RawMaterial/office_0/textures/ 
