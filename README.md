# exam_git


# exam_git
 #partie gradient boosting (yahia zakaria messaoudi)

 je m'excuse pour le basard dans le notebook et j'ai u des problemme avec les commit pour push le model aussi mais j'ai reuissi a la fin 

 
## Predicting Diabetes Type with Gradient Boosting

In this project, we aim to predict diabetes type using gradient boosting, with a class imbalance of 2 minority classes to 1 majority class. Gradient boosting is an ensemble machine learning technique that combines multiple weak models to create a strong predictive model.

### Data Preprocessing

Before training the gradient boosting model, we need to preprocess the data. This may involve handling missing values, scaling numerical features, encoding categorical variables, and splitting the dataset into training and testing sets.

### Handling Class Imbalance

Since we have a class imbalance of 2 minority classes to 1 majority class, we need to address this issue to prevent the model from being biased towards the majority class. There are several techniques we can use, such as:

- Undersampling the majority class: This involves randomly removing samples from the majority class to balance the dataset.
- Using class weights: This involves assigning higher weights to the minority classes during model training.

### Model Training

Once the data is preprocessed and the class imbalance is handled, we can proceed with training the gradient boosting model. We'll use a suitable library such as XGBoost or LightGBM to train the model on the preprocessed dataset.

### Model Evaluation

After training the model, we need to evaluate its performance. We can use various evaluation metrics such as accuracy, precision, recall, and F1-score to assess how well the model is predicting the diabetes type. Additionally, we can visualize the model's performance using confusion matrices or ROC curves.

### Conclusion

In this project, we successfully predicted diabetes type using gradient boosting with a 2 minority classes to 1 majority class ratio. By handling the class imbalance and training a robust model, we were able to achieve accurate predictions for diabetes type classification.
#### partie docker 
vue que les autre m'on pas push leur model on a pas pu finir l'image et le main 
j'ai commencer avec docker 

PS C:\Users\zack> docker volume create my_model_volume
error during connect: this error may indicate that the docker daemon is not running: Post "http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.24/volumes/create": open //./pipe/docker_engine: The system cannot find the file specified.
PS C:\Users\zack> docker volume create my_model_volume
my_model_volume
PS C:\Users\zack> docker cp classification_model.pkl my_model_volume:/path/in/volume/
CreateFile C:\Users\zack\classification_model.pkl: The system cannot find the file specified.
PS C:\Users\zack> docker cp C:\Users\zack\Desktop\Nouveau dossier (2)\exam_git\classification_model.pkl my_model_volume:/path/in/volume/
"docker cp" requires exactly 2 arguments.
See 'docker cp --help'.

Usage:  docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-
        docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH

Copy files/folders between a container and the local filesystem
PS C:\Users\zack> docker run -v my_model_volume:/target_volume -w /target_volume -v C:\Users\zack\Desktop\Nouveau\ dossier\ (2)\exam_git:/host busybox cp /host/classification_model.pkl .
docker: invalid reference format.
See 'docker run --help'.
PS C:\Users\zack> docker run -v my_model_volume:/target_volume -w /target_volume -v /c/Users/zack/Desktop/Nouveau\ dossier\ \(2\)/exam_git:/host busybox cp /host/classification_model.pkl .
2\ : Le terme «2\» n'est pas reconnu comme nom d'applet de commande, fonction, fichier de script ou programme
exécutable. Vérifiez l'orthographe du nom, ou si un chemin d'accès existe, vérifiez que le chemin d'accès est correct
et réessayez.
Au caractère Ligne:1 : 109
+ ... target_volume -v /c/Users/zack/Desktop/Nouveau\ dossier\ \(2\)/exam_g ...
+                                                                ~~
    + CategoryInfo          : ObjectNotFound: (2\:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\Users\zack> docker run -v my_model_volume:/target_volume -w /target_volume -v C:\Users\zack\Desktop\Nouveau\ dossier\ (2)\exam_git:/host busybox cp /host/classification_model.pkl .
docker: invalid reference format.
See 'docker run --help'.
PS C:\Users\zack> docker run -v my_model_volume:/target_volume -w /target_volume -v "C:\Users\zack\Desktop\Nouveau dossier (2)\exam_git:/host" busybox cp /host/classification_model.pkl .
Unable to find image 'busybox:latest' locally
latest: Pulling from library/busybox
6672f60b6ba8: Pull complete
Digest: sha256:1ceb872bcc68a8fcd34c97952658b58086affdcb604c90c1dee2735bde5edc2f
Status: Downloaded newer image for busybox:latest
PS C:\Users\zack> docker run -v my_model_volume:/path/in/container my_image
Unable to find image 'my_image:latest' locally
docker: Error response from daemon: pull access denied for my_image, repository does not exist or may require 'docker login': denied: requested access to the resource is denied.
See 'docker run --help'.
PS C:\Users\zack> docker build -t my_image .
[+] Building 0.1s (2/2) FINISHED                                                                         docker:default
 => [internal] load build definition from Dockerfile                                                               0.1s
 => => transferring dockerfile: 2B                                                                                 0.0s
 => [internal] load .dockerignore                                                                                  0.1s
 => => transferring context: 2B                                                                                    0.0s
ERROR: failed to solve: failed to read dockerfile: open /var/lib/docker/tmp/buildkit-mount3233568858/Dockerfile: no such file or directory
PS C:\Users\zack> docker tag my_image:latest my_image:1.0
Error response from daemon: No such image: my_image:latest
PS C:\Users\zack> docker tag my_image:latest my_image:1.0
Error response from daemon: No such image: my_image:latest
PS C:\Users\zack> docker run -v my_model_volume:/path/in/container my_image
Unable to find image 'my_image:latest' locally
docker: Error response from daemon: pull access denied for my_image, repository does not exist or may require 'docker login': denied: requested access to the resource is denied.
See 'docker run --help'.
PS C:\Users\zack> docker build -t my_image .
[+] Building 0.1s (2/2) FINISHED                                                                         docker:default
 => [internal] load .dockerignore                                                                                  0.0s
 => => transferring context: 2B                                                                                    0.0s
 => [internal] load build definition from Dockerfile                                                               0.0s
 => => transferring dockerfile: 2B                                                                                 0.0s
ERROR: failed to solve: failed to read dockerfile: open /var/lib/docker/tmp/buildkit-mount952962391/Dockerfile: no such file or directory
PS C:\Users\zack> cd /path/to/your/dockerfile
cd : Impossible de trouver le chemin d'accès « C:\path\to\your\dockerfile », car il n'existe pas.
Au caractère Ligne:1 : 1
+ cd /path/to/your/dockerfile
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\path\to\your\dockerfile:String) [Set-Location], ItemNotFoundExceptio
   n
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.SetLocationCommand

PS C:\Users\zack> docker build -t my_image .
[+] Building 0.1s (2/2) FINISHED                                                                         docker:default
 => [internal] load build definition from Dockerfile                                                               0.0s
 => => transferring dockerfile: 2B                                                                                 0.0s
 => [internal] load .dockerignore                                                                                  0.0s
 => => transferring context: 2B                                                                                    0.0s
ERROR: failed to solve: failed to read dockerfile: open /var/lib/docker/tmp/buildkit-mount602189433/Dockerfile: no such file or directory
PS C:\Users\zack> docker pull python
Using default tag: latest
latest: Pulling from library/python
90e5e7d8b87a: Pull complete
27e1a8ca91d3: Pull complete
d3a767d1d12e: Pull complete
711be5dc5044: Pull complete
45df5ffe8c3b: Pull complete
cdc2c85f810b: Pull complete
f6a11d2ee0cf: Pull complete
8db447a102db: Pull complete
Digest: sha256:a25e0cf180ee1bbbc103bb39508fb12b75020427abaaff83bec5999454c3735f
Status: Downloaded newer image for python:latest
docker.io/library/python:latest

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview python
PS C:\Users\zack> docker build -t my_image .
[+] Building 0.0s (0/0)                                                                                  docker:default
2023/12/14 17:13:41 http2: server: error reading preface from client //./pipe/docker_engine: file has already been close[+] Building 0.2s (2/2) FINISHED                                                                         docker:default
 => [internal] load .dockerignore                                                                                  0.1s
 => => transferring context: 2B                                                                                    0.1s
 => [internal] load build definition from Dockerfile                                                               0.1s
 => => transferring dockerfile: 2B                                                                                 0.1s
ERROR: failed to solve: failed to read dockerfile: open /var/lib/docker/tmp/buildkit-mount3727576760/Dockerfile: no such
$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp python:3 python your-daemon-or-script.py

