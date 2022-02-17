# Automatic Die Change System
※The code property belongs to the lab, so it is not allowed to open source.

This project cooperates with mechanic students. They added a die storage module to the existing machine, and I developed and merged the system function with the current machine program.

In the concept of a sequence diagram, the system will involve three objects machine/storage module, PC, PLC.
* machine/die storage: This machine is a stamping simulator driven by ball screws. The die storage is added because we want to stamp two objects through automatic die change.
* PC: Our machine is PC-Based controls.
* PLC: Sensors on the die storage will store the signal in the PLC register. PLC also controls the gripper jaw and pneumatic cylinder.

# System control interface
Control Interface includes five functions
* Storage reset: Reset the die storage position to the upper layer. This means the pneumatic cylinder can directly push the main die into the punch.
* Main die: Make sure the storage is at the upper layer and push the main die into the punch. The right part of the control interface will display as the middle picture below then both buttons (main, minor die) will be disabled.
* Minor die: Make sure the storage is at the lower layer and push the minor die into the punch. The right part of the control interface will display as the right picture below then both buttons (main, minor die) will be disabled.
* Change die: If there is no die in the punch, this button will be disabled. Otherwise, the die in the punch will change with the other one. 
* Return die: Return the die to the storage.
![image](https://user-images.githubusercontent.com/88305396/151932676-3656d6fd-fcb8-47e3-9ec5-71ede9c41a9e.png)

# Functions flow chart
![刀庫復位](https://user-images.githubusercontent.com/88305396/152029704-05aca64f-a12d-45ca-8e0c-e21f07215d51.png)
![主刀副刀](https://user-images.githubusercontent.com/88305396/152031561-99571bdb-ad6b-4f71-852e-fa3502ab7106.png)
![換刀退刀](https://user-images.githubusercontent.com/88305396/152031578-ce9f64ae-7dd4-41ff-8fc7-7ab494fd6d9b.png)
  
# Automatic die change demo
By marking(object is main or minor die) the composition file, when the next object to stamp is different from the die in the punch, it will execute the corresponding function.

At the beginning of the video, the punch is empty, and the composition shows that we will first stamp the triangles(main die) and then the flowers(minor die), so the main die function is activated, after all the triangles object is stamped, the change die function is executed to finish the progress.


https://user-images.githubusercontent.com/99638331/154245534-3a4868d4-6694-46e2-9f34-a5a09633fa88.mp4

