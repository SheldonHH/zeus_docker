FROM boscore/builder as builder

RUN apt-get update && apt-get install -y wget sudo curl
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install openssl ca-certificates wget cmake python3 g++ vim net-tools lsof supervisor

RUN apt-get install -y git-core libtool build-essential
RUN wget https://github.com/EOSIO/eosio.cdt/releases/download/v1.6.1/eosio.cdt_1.6.1-1_amd64.deb
RUN apt-get update && sudo apt install -y ./eosio.cdt_1.6.1-1_amd64.deb
RUN wget https://github.com/EOSIO/eos/releases/download/v1.7.1/eosio_1.7.1-1-ubuntu-18.04_amd64.deb
RUN apt-get update && sudo apt install -y ./eosio_1.7.1-1-ubuntu-18.04_amd64.deb
RUN apt-get update && sudo apt install -y nodejs
	&& sudo apt-get -y install npm && sudo npm cache clean -f && sudo npm install -g n && sudo n stable
RUN npm install -g cnpm --registry=https://registry.npm.taobao.org
RUN cnpm install -g @liquidapps/zeus-cmd && cnpm upgrade -g @liquidapps/zeus-cmd
