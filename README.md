# IIEC_DOCKER_PROJECT
using docker-compose and wordpress i perform "face detection program" from which data{like comments,email id,code} of that website is stored in mysql databases which is permant storage act as centralised storage for no of container launched using same storage and network
my website contains 5 webpages which contain face detection machine learning program .last page on my website is contact us on which client enter their email id,name,comment which are permantly stored on mysql database
to crate website i perform following step:
as we know wordpress is works on mysql databases and used to create satic and dynamic website.
we install wordpress and mysql database software on docker container which launched on base os.
after this we can create website on wordpress .
if requirment is we required more container to balnce laod on server hence we need to launch more container .
instead of each time installing  wordpress and mysql on new docker container we create new image by using that container os which already contain wordpress and mysql.
from this image we can launch unlimited docker container .
if load on server is large then we launch another docker os within 1 sec  which is launched using same network and same permant storage
due to this client can access website on any of the container 
after launching container os we can access wordpress from local host but if we required to access it  from other devices[windows] here we required public  router ip.
base os redhat ip act as public router ip of container os .
during launching container we need to specify the port no through router connect to client our server. 
e.g   -p 8080:80  here windows[client] contact to base os  on port 8080 which acta a router and forward request to port 80 of container os where client access server
but after every time on booting redhat[local host] we need to launch to container so it is wastage of time and client can not able to access our website 
hence need script that automatically launch the docker container as we boot our base os that program tool-name is docker-compose 
docker-compose contain docker-compose.yml file where we enter our command to start our container then client can access our website or can acces wordpesss at port 8080 of local host 
docker-compose is not intelligent tool like a openshift which launch new  container  whenever onwe container using same network and same permant volume
