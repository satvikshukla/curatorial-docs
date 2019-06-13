# Curatorial AI tool

### Resons for building current version of the tool

- Interacting through terminal is not the best and the easiest way to play around
and experiment. So it was necessary to have a tool that made it easier to interact
with th cycleGAN model that had been trained at the moment.
- Running applications is not easy, especially if it uses some Machine Learning library.
Installing the languages, setting up the environment, downloading libraries, etc. make it 
harder to get something up and running easily. This led to building a tool that was able 
to run on any platform (Mac, Windows, Linux) in the shortest possible amount of time and 
also with the least effort.

### Steps to get the tool up and running

- The only thing necessary to install is Docker. To install if for your platform, refer to the 
following link: https://docs.docker.com/install/. If you are on Windows and face some issues 
regarding Hyper-V or virtualization, refer to the following links: 
https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v, 
https://www.howtogeek.com/213795/how-to-enable-intel-vt-x-in-your-computers-bios-or-uefi-firmware/.
- Once docker is up and **running**, download the `docker-compose.yml` file present in this repository.
- Open up terminal (on windows use powershell) on your system and navigate to the location of the download 
`docker-compose.yml` file. (Use this resource if you are unfamilar with navigating to directories through 
terminal: 
https://www.macworld.com/article/2042378/master-the-command-line-navigating-files-and-folders.html)
- Once you are in the same directory as the file, run the command `docker-compose up`. This should get
the application up and running after some automatic downloads. 

Note: In the last step, you might need root priviliges to run the command. If so, run 
`sudo docker-compose.yml`.

- If successful, you should see the downloads that were going on have finished and new services
have started in your terminal with either of `frontend`, `backend`, or `database` showing up
towards the left side of the terminal. To try out the tool, go to `http://localhost:5000`.
This implies the process was successfull, open the url in browser to use the tool.
- To stop the cool, go back to the terminal and press `ctrl + c`.


### Cleanup steps

Docker downloads `images` that contain the code and resources required to run it. To run the code, it
creates isolated environments to run the code in and volumes to store some temporary data. After you
have stopped the application, they will persist and it would be advisable to remove them. 

- To remove the containers use the command: `docker rm $(docker ps -a -q)`.
- To remove the volumes use the command: `docker volume prune -f`.

If you are sure that you will not be using the tool again, you can remove the images also, that store
all the base sources. To do so use the command `docker rmi $(docker images -q)`.

Note: If the commands do not run, you might need root priviliges. In that case, each one will change to 
`sudo docker rm $(sudo docker ps -a -q)`, `sudo docker rm $(sudo docker ps -a -q)`, and 
`sudo docker rmi $(sudo docker images -q)` respectively.