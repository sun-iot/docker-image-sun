# 指定基镜像 centos
FROM centos:centos7.7.1908

MAINTAINER      Fisher "sunyang.iot@gmail.com"
# 先执行更新

# 复制jdk到指定目录
RUN /bin/mkdir -p  /opt/software
RUN /bin/mkdir -p /opt/module
ADD jdk-8u201-linux-x64.tar.gz /opt/module

# 配置jdk环境
ENV JAVA_HOME /opt/module/jdk1.8.0_201
ENV PATH $PATH:$JAVA_HOME/bin
 
# 检测java版本，确认是否安装成功
RUN java -version

ADD scala-2.11.11.tgz /opt/module

# 配置SCALA 环境
ENV SCALA_HOME /opt/module/scala-2.11.11
ENV PATH $PATH:$SCALA_HOME/bin

RUN ssh-keygen -t rsa -f ~/.ssh/id_rsa -P '' && \
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

CMD [ "sh", "-c", "service ssh start;bash"]
