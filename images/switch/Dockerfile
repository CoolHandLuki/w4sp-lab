#import from our base image
FROM w4sp/labs:base

RUN apt-get install -y dnsmasq software-properties-common

#add suricata repo
RUN add-apt-repository -y ppa:oisf/suricata-stable
# RUN wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | apt-key add -
# RUN echo "deb http://packages.elastic.co/logstash/2.0/debian jessie main" | tee -a /etc/apt/sources.list
RUN apt-get update

#install suricata and logstah
RUN apt-get install -y suricata openjdk-8-jre-headless
RUN wget -q --no-check-certificate https://artifacts.elastic.co/downloads/logstash/logstash-5.2.0.deb ; dpkg -i logstash-5.2.0.deb
ADD logstash.conf /etc/logstash/conf.d/logstash.conf
ADD suricata.yaml /etc/suricata/suricata.yaml
RUN touch /var/log/suricata/eve.json

#install lldp
RUN apt-get -y install lldpd

#add the startup script to add nics to the bridge automagically
ADD start_sw.py /start_sw.py

#add supervisord script and remove the dhclient one
ADD supervisor_sw.conf /etc/supervisor/conf.d/supervisor_sw.conf
RUN rm -f /etc/supervisor/conf.d/supervisor_dhclient.conf
