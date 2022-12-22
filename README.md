# 0. ����
- ��Ŀ��Դ https://github.com/ethz-asl/rotors_simulator

# 1. ����
```shell
mkdir -p ~/rotors_ws/src
cd ~/rotors_ws/src
git clone https://github.com/COOLAS-LAB/rotors_simulator
cd ..
catkin_make
```

## 2. ����
- ��������
```shell
cd ~/rotors_ws/
source devel/setup.bash
roslaunch rotors_gazebo single_uav.launch
```
- �������
```shell
cd ~/rotors_ws/
source devel/setup.bash
roslaunch rotors_gazebo multi_uav.launch
```

- Ĭ�Ͼ����� `ardrone` ���������˻�

## 3. ���ò���˵��
- `~/rotors_ws/rotors_simulator/rotors_gazebo/launch/spawn_mav.launch` ��
  ```shell
  <arg name="x" default="0.0"/>
  <arg name="y" default="0.0"/>
  <arg name="z" default="0.1"/>
  ```
  �������˻���ʼλ�ã�`single_uav.launch` �� `multi_uav.launch` ������`spawn_mav.launch` �ļ���ֻ�޸��� `y` ֵ���������ֲ��䡣
- `~/rotors_ws/rotors_simulator/rotors_gazebo/launch/multi_mav.launch` �У�ÿһ�� `<group ns="">` ��ǩ����������µ����˻���`ns` ָʾ����ǰ׺����

## 4. ���û���˵��
- `/ardrone_{x}/command/pose`�����˻�λ�˿��ƻ��⣬�������˻�λ��
- `/ardrone_{x}/odometry_sensor{x}/odometry`�����˻���̼ƻ��⣬��������ϵ�µ�����
- `/ardrone_{x}/vi_sensor/camera_depth/camera/camera_info`���������ڲ�
- `/ardrone_{x}/vi_sensor/camera_depth/camera/image_raw`��ԭͼ
- `/ardrone_{x}/vi_sensor/camera_depth/depth/disparity`�����ͼ
- `/ardrone_{x}/vi_sensor/left/image_raw`����Ŀ���ͼ
- `/ardrone_{x}/vi_sensor/right/image_raw`����Ŀ���ͼ


## 5. �޸����λ��
- �޸� `rotors_simulator/rotors_description/urdf/mav_with_vi_sensor.gazebo`�е�`<origin xyz="0.1 0.0 -0.03" rpy="0.0 0.1 0.0" />`������ڻ����λ�ã�`x,y,z`Ϊλ�ã�`rpy`Ϊ��תŷ����

## 6. ��������ģ��
- Ŀǰ���� gazebo ��ֱ�Ӳ������
- to be continue