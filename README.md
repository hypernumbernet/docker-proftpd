    docker run -d --restart unless-stopped --name proftpd \
    --net=host \
    -e FTP_PORT=21 \
    -e FTP_PASSIVE_PORTS_MIN 30000 \
    -e FTP_PASSIVE_PORTS_MAX 30015 \
    -e MASQUERADE_ADDRESS=10.1.2.3 \
    -e USERNAME=username -e PASSWORD=password \
    -v `pwd`/ftp:/ftp \
    hypernumbernet/proftpd

It can be used in passive mode.

You can deploy this docker image with Rancher.
[My Rancher Catalog](https://github.com/hypernumbernet/rancher-catalog)

Tested client: FileZilla, Windows10 Explorer, FFFTP
