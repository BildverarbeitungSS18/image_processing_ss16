# FU Berlin - Image Processing SS 16

The assignments will be published to this repository.
All assignments will be IPython Notebooks. That you have to complete.

## Work flow

The rough workflow is:
1. You clone this repository.
2. Edit the exercises.
3. Push it to your private repository.
4. I fetch your code when the assignment is due. (Every Wednesday at 16 o'clock)
5. You fetch the latest assignments from this repository.

It is required to use private git repositories.
The university offers free private repositories [here](https://git.imp.fu-berlin.de/)
or you can get [5 GitHub repositories for free](https://education.github.com/) as a student.

First clone this repository:

```
$ git clone --origin upstream https://github.com/berleon/image_processing_ss16
```

Get into the new folder

```
$ cd image_processing_ss16
```

Add your remote

```
$ git remote add origin <your git repo url>
```

Please clear the notebook's output before committing. Otherwise the repository
size can get pretty big.

The best thing is to setup a `pre-commit` hook that removes the outputs before
the files are committed:

```
$ ln -s ../../nb_strip_output.py .git/hooks/pre-commit
```

Otherwise you manually clean the output with `Cell -> All Output -> Clear` or
use the `nb_strip_output.py <filename>` script.

To get the latest assignments into your repository see [how to sync a fork](https://help.github.com/articles/syncing-a-fork/).

Paste a link to your repository into the kvv assignment box.
Make sure that I have read and write rights on your repository.
My github account is `berleon` and my FU gitlab account is `leonsixt`.

## Docker

There exists a script for a [docker](https://www.docker.com/) image.
All the libraries we will use are included in this image.
It is recommended to use the image, but you are free to setup the environment
for yourself.

First [install docker](https://docs.docker.com/engine/installation/) on your computer.

Build the image:

```
$ ./docker_build.sh
```
The build script will create a user with your username and uid inside the image.
It may take some minutes until the image is built.

If you don't have a bash you can manually edit the `Dockerfile.sample`.
See the docker documentation for [details](https://docs.docker.com/)

To run the image:

```
$ ./docker_start.sh
```

Now visit [localhost:8888](http://localhost:8888). Jupyter Notebook
should be ready to use.
