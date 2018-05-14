FROM amazonlinux:latest
RUN yum -y install which unzip aws-cli

# Mimic AWS Lambda Python 3.6 Runtime Environment
RUN yum install -y python36
RUN python3 -m pip install -U "botocore==1.9.3"
RUN python3 -m pip install -U "boto3==1.7.0"
RUN python3 -m pip install -U "python-dateutil==2.7.2"

ADD fetch_and_run.sh /usr/local/bin/fetch_and_run.sh
WORKDIR /tmp
USER nobody
ENTRYPOINT ["/usr/local/bin/fetch_and_run.sh"]
