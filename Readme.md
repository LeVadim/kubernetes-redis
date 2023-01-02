Hi Student!

Thanks for attending my course!

In this github repository you will find needed files in order to deploy Redis in Kubernetes.

I have attached the code base for Redis deployed on Kubernetes that you will use in this chapter.  If you get stuck at any moment, please feel free to refer to this code.

Just in case, please see below an explanation of each folder:

`config` - directory where we have stored "redis.conf"

`.gitignore` - list of files that you not be pushed to GitHub. (your local files & installed packages that won't be needed in production

`Dockerfile` - File that Docker is using in order to compile a server image

`cloudbuild-production.yaml` - File that google cloud is using in order to run a deployment, create an image and deploy it to Kubernetes in the master/production environment

Make sure that these files are deployed on your GitHub repository.

If you do encounter any issues or you have suggestions, please email me at vadim.d.makarenko@gmail.com , will be glad to connect and hear your feedback, as it is very important to improve this course!

Vadim Makarenko
