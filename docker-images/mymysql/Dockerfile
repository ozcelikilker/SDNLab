#FROM mysql:5.7 
#RUN apt-get update; exit 0 
#RUN apt-get install -y net-tools iproute2 iputils-ping 

#Updated on 14.02.2025 for compatibility.
#If you encounter any issues, you may need to modify the relevant Dockerfile to match your system.
FROM mysql:5.7
# Check for the operating system:
RUN if [ -f /etc/debian_version ]; then \
        apt-get update && apt-get install -y net-tools iproute2 iputils-ping && apt-get clean; \
    elif [ -f /etc/redhat-release ]; then \
        rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022 && \
        yum install -y net-tools iproute iputils && \
        yum clean all; \
    else \
        echo "Unsupported OS. Please modify the Dockerfile accordingly." && exit 1; \
    fi

CMD ["mysqld"]
