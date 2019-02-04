FROM nginx

ENV SRV_ADDRESS="app"
ENV SRV_PORT="9000"

COPY nginx.conf /etc/nginx/nginx.conf


RUN /bin/sed -i "s/<SRV_ADDRESS>/$SRV_ADDRESS/" /etc/nginx/nginx.conf
RUN /bin/sed -i "s/<SRV_PORT>/$SRV_PORT/" /etc/nginx/nginx.conf
