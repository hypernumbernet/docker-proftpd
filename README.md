    docker pull hypernumbernet/proftpd

    docker run -d --restart unless-stopped --name proftpd \
    --net=host \
    -e FTP_PORT=21 \
    -e FTP_PASSIVE_PORTS_MIN 30000 \
    -e ENV FTP_PASSIVE_PORTS_MAX 30015 \
    -e MASQUERADE_ADDRESS=10.1.2.3 \
    -e USERNAME=username -e PASSWORD=password \
    -v `pwd`/ftp:/ftp \
    hypernumbernet/proftpd

Using Passive mode.
Tested client: FileZilla, Windows10 Explorer, FFFTP
