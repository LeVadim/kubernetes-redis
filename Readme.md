# Hi! Thanks for attending my course! In this github repository you will find needed files in order to deploy Redis application.

I have attached the code base for Redis deployed on Kubernetes that you will use in this chapter.  If you get stuck at any moment, please feel free to refer to this code.

Just in case, please see below an explanation of each folder:

`config` - directory where we have stored "redis.conf"

`.gitignore` - list of files that you not be pushed to GitHub. (your local files & installed packages that won't be needed in production

`Dockerfile` - File that Docker is using in order to compile a server image

`cloudbuild-production.yaml` - File that google cloud is using in order to run a deployment, create an image and deploy it to Kubernetes in the master/production environment

Make sure that these files are deployed on your GitHub repository.

# Build & Run docker locally:
`docker build -t redisdocker .`

`docker run -p 6379:6379 redisdocker`

`If you want to connect to your redis instance, you'll need to disable protected mode in redis.conf, Line 94, but changed "yes" to "no" - protected-mode no, then rebuilding docker image and then you'll be able to telnet localhost 6379`

# Additionally, please refer to `Cheatsheet.md` for list of useful commands or see below.
I suggest always having some sort of "Cheat Sheet".  This is where you store all the commands that you use in your daily life.  It doesn't make sense to memorize every single command, it is just not feasible.  This is why I suggest saving this cheat sheet that you will use in this course and improving it later on as you go.

Cheatsheet:

`docker build --platform amd64 -t helloworld .`

`docker images`

`docker rmi $(docker images -a -q)`

`docker rmi $(docker ps -a -q)`

`docker run -i -t -p 80:80 helloworld`

`docker ps`

Run the container + forward port to local port

`docker run -i -t -p 80:80 helloworld`

List processes/containers

`docker ps`

Remove container - `docker rm container_id`

Remove image - `docker rmi image_id`

How to enter into shell of an instance?

`docker exec -it "id” bash`

Google

`gcloud auth login vadim@ctomentorship.com`

`gcloud config set project inner-catfish-339817`

-) `docker tag helloworld us.gcr.io/inner-catfish-339817/helloworld:0.0.1`

-) `docker push us.gcr.io/inner-catfish-339817/helloworld:0.0.1`

Quickly switch between projects:

`gcloud config set project inner-catfish-339817; gcloud container clusters get-credentials autopilot-cluster-1 —zone us-east4;`

SECRETS

`kubectl create secret generic env-credentials --from-file=env-credentials.json=env-credentials.json`

`kubectl create secret tls my-tls-secret --key example.key --cert example.crt`

Connecting to a Pod:

`kubectl exec -ti YOUR_POD_ID_HERE sh`

Want to speed up your development speed? Include long commands to your ~/.bash_profile by adding an alias
1) `vim ~/.bash_profile`
2) add this below:
For PHP users:
`alias composer="php /usr/local/bin/composer.phar"`
`alias updsdk="php /usr/local/bin/composer.phar update --ignore-platform-reqs; cd ../../..; git add .; git commit -m 'sdk upd'; git push;"`
`alias test="php artisan test"`

Easy command for past commit & push

`alias gpush="git add .; git commit -m 'sdk upd'; git push;"`

Authenticate with different Google-Cloud environments/accounts

`alias testcloud="gcloud config set project inner-catfish-339817; gcloud container clusters get-credentials autopilot-cluster-1 —zone us-east4;"`


# Thank you

If you do encounter any issues or you have suggestions, please email me at vadim.d.makarenko@gmail.com , will be glad to connect and hear your feedback, as it is very important to improve this course!

Vadim Makarenko
