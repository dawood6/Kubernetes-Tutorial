Hello Dears

Read full description because it contains all information about how to make:
repository on dockerhub
making docker image
making docker container
push image on dockerhub
making Kubernetes Deployment
making Kubernetes Service .

In this GitHub Repository you will see 3 Files:

dockerfile
deployment.yaml
service.yaml

We are using yaml format because it is much easier than json format.

For running Kubernetes you must know how to run Docker. Now for making image on Docker hub you have to save this above dockerfile in same folder which contains your website code and after that make a repository dockerhub and name the repository the same name as you eould name the image.

after making repository run this command

\$ sudo docker build -t <imagename> .
  
  
Note: name same as you make docker hub repository and replace this <imagename> with your image name dont put your image name inside these <> brackets .

After this run this command for Seeing image id

\$ sudo docker image ls

After you run this command on command line and make sure you are on the right folder where your code is you will see all the images that you build before but for new bees this is first time so you will only see this image and kubernetes images. Notice your image by the name that you have given and copy the imageid.

After this run this command

\$ sudo docker tag <imgid> <dockerhubusername>/<imagename:tag>
                      |             |              |
this will be your image id that you | will receive | after doing above mentioned process  
                                    |              |
             this will be your docker hub username |
this will be your image name and :tag means the tag you have to give this image like :latest or etc

    after this above process the image has been successfully tagged and final and last process is left

\$ sudo docker push <dockerhubusername>/<imagename:tag>
After this command your image will be successfully pushed to dockerhub

And After this check in dockerhub repository it will have your image and now for making container you will have to run this command

\$ sudo docker run -d --name <containername> -p 8000:80 <dockerhubusername>/<imagename:tag>

with this command a container for your mage will be made and on port 8000 and :80 is target port always remain 80 <containername> will be replace by your name which would you give to your container

now type in google adddress bar

localhost:8000

## you will see you website

End of portion Docker

Now Kubernetes

You will see above two files with yaml extension

first you will run

\$ minikube start

if you have install minikube if not then install it from here

https://kubernetes.io/docs/tasks/tools/install-minikube/

this web will give you full information about installing minikube

Now run command

\$ minikube status

Output

host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

it means right your minikube is ready

now run

\$ nano deployment.yaml

it opens text editor now copy paste my deployment.yaml as above file but give it your name and your image

and save and run

\$ kubectl create -f deployment.yaml

and your deployment will be created

and now we will create service

\$ nano service.yaml

it opens text editor now copy paste my service.yaml as above file

and save and run

\$ kubectl create -f service.yaml

and your service will be created

and for seeing it on web

you will have to run

\$ sudo miniube ip

it gives your minikube ip

and also run

\$ kuectl get service

it will show your service that you have made

and now copy your minikube ip and paste it on google address bar and put colon after it with no space
and and copy your service second port means:

9000/your port/tcp
|
copy this one

    and
    like this

    your minikube ip:and above you service port

    and enter
    you will see your web if not then
    contact me

    dawoodsadiq171@gmail.com
