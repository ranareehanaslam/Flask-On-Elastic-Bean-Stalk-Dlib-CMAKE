# FlaskOnElasticBeanStalkDlibCMAKE
Flask On Elastic Bean Stalk with Dlib and cMake c++ Libraries

#STEPS TO FOLLOW 
Steps:
Install Amazon Cli On Windows/Any Other Operating System
pip install virtualenv
activate the virtual env
pip install all the libraries used inside the project

setup config file .exextensions folder with anything.conf

eb init lastytry --platform "Python 3.11" --region ca-central-1

eb create lastytry --timeout 60







sudo yum update -y
sudo yum install gcc-c++ cmake -y
sudo yum install python3-devel -y
sudo yum install boost boost-devel boost-python3 boost-python3-devel -y
sudo yum install openblas openblas-devel -y
sudo yum install lapack lapack-devel -y
sudo yum install libX11 libX11-devel -y
sudo yum install libpng libpng-devel -y
sudo yum install mesa-libGL -y
sudo yum install ffmpeg-devel
sudo yum install libjpeg-turbo libjpeg-turbo-devel  -y
wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm	
sudo rpm -ihv --nodeps ./epel-release-latest-8.noarch.rpm	
sudo /usr/bin/crb enable
wget https://files.pythonhosted.org/packages/2e/9d/4e1003c044bdb07f7c0d83ae87d694e10e5a6c296b84566aa9a6ec9eed2a/dlib-19.24.2.tar.gz
tar xvf dlib-19.24.tar.bz2
cd /tmp
wget https://files.pythonhosted.org/packages/2e/9d/4e1003c044bdb07f7c0d83ae87d694e10e5a6c296b84566aa9a6ec9eed2a/dlib-19.24.2.tar.gz
tar xvf dlib-19.24.2.tar.gz
cd dlib-19.24.2/
sudo PYTHONPATH="/var/app/venv/staging-LQM1lest/lib64/python3.11/site-packages:$PYTHONPATH" python3.11 setup.py install --prefix=/var/app/venv/staging-LQM1lest
sudo python3.11 setup.py install --home==/var/app/venv/staging-LQM1lest/lib/python3.11/site-packages/
sudo python3.11 setup.py install 
sudo python3.11 setup.py install 
cd /











/var/app/venv/staging-LQM1lest/lib/python3.11/site-packages

/etc/nginx/conf.d/proxy.conf==client_max_body_size 50M;


