РЕАЛИЗАЦИЯ НА ROS2 через docker

Необходимо открыть 4 терминала

--- 
### Заходим в докер

    docker start kuka 
    docker exec -it kuka bash 

В каждом терминале прописываем перед запуском программы 

    cd ~/workspace/
    source devel/setup.bash 

На хосте прописываем для разрешение действий в докере:
    
    xhost +local:docker
---
### Подключаем kuka

Проверяем подключение Ethernet кабель

    ip. 192.168.1.100
    255.255.255.0

Запускаем управлние 

    roslaunch kuka_rsi_hw_interface test_hardware_interface.launch sim:=false

Запустите move_group для управления роботом с помощью Moveit

    roslaunch real_kuka_kr3_moveit_config move_group.launch
---
### Подключение камеры 

Запуск программы 

    roslaunch pylon_camera pylon_camera_node.launch

Проверка изображения 

    rosrun rqt_image_view rqt_image_view 
---
### Запуск программы управления

Заходим в деректорию 

    сd ~/workspace/src/KUKA-ROS-Control/scripts

Запуск программы

    python3 finallll.py



