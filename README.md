# Flask On Elastic Beanstalk with Dlib and CMake C++ Libraries

## Steps to Follow

1. Open the command prompt as an administrator.
2. Move to the project directory.
3. Install `virtualenv` by running the command `pip install virtualenv`.
4. Create a virtual environment by executing the command `virtualenv testing`.
5. Navigate to the `Scripts` folder inside the `testing` directory.
6. Activate the virtual environment by running the `activate` command.
7. Go back to the previous directory using `cd ..`.
8. Install all the libraries required for the project.
9. Run & Test your project
10. Freeze(Generate) the requirements.txt file
11. Set up the config file `.ebextensions` folder with `custom_ami or any name.conf`.



## Nginx Configuration to Fix 413 Request Entity Too Large nginx

Add the following line to the `.platform\nginx\conf.d\elasticbeanstalk\application.conf` file:

```
client_max_body_size 50M;
```





Add the following content to the file `.ebextensions\custom_ami.config`:

## Deployment Script

```bash
sudo yum update -y
sudo yum install gcc-c++ cmake -y
sudo yum install python3-devel -y
sudo yum install boost boost-devel boost-python3 boost-python3-devel -y
sudo yum install openblas openblas-devel -y
sudo yum install lapack lapack-devel -y
sudo yum install libX11 libX11-devel -y
sudo yum install libpng libpng-devel -y
sudo yum install mesa-libGL -y
sudo yum install ffmpeg-devel -y
sudo yum install libjpeg-turbo libjpeg-turbo-devel -y

wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
sudo rpm -ihv --nodeps ./epel-release-latest-8.noarch.rpm
sudo /usr/bin/crb enable

cd /tmp
wget https://files.pythonhosted.org/packages/2e/9d/4e1003c044bdb07f7c0d83ae87d694e10e5a6c296b84566aa9a6ec9eed2a/dlib-19.24.2.tar.gz
tar xvf dlib-19.24.2.tar.gz
cd dlib-19.24.2/

sudo PYTHONPATH="/var/app/venv/staging-LQM1lest/lib64/python3.11/site-packages:$PYTHONPATH" python3.11 setup.py install --prefix=/var/app/venv/staging-LQM1lest
sudo python3.11 setup.py install --home==/var/app/venv/staging-LQM1lest/lib/python3.11/site-packages/
sudo python3.11 setup.py install

cd /
```

10. Install AWS CLI
11. Install pip install awsebcli
12. Initialize Elastic Beanstalk with the following command:
    ```
    eb init lastytry --platform "Python 3.11" --region eu-north-1
    ```
13. Create an Elastic Beanstalk environment with the following command:
    ```
    eb create lastytry --timeout 60
    ```




