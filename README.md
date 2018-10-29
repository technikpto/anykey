AnyKey Coin integration/staging repository
======================================


***

Quick installation of the AnyKeyCoin daemon under linux. See detailed instructions there [build-unix.md](build-unix.md)

Installation of libraries (using root user):

    add-apt-repository ppa:bitcoin/bitcoin -y
    apt-get update
    apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    apt-get install -y libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    apt-get install -y libdb4.8-dev libdb4.8++-dev

Cloning the repository and compiling (use any user with the sudo group):

    cd
    git clone https://github.com/technikpto/anykey.git
    cd anykey
    ./autogen.sh
    ./configure
    sudo make install
    cd src
    sudo strip anykeycoind
    sudo strip anykeycoin-cli
    sudo strip anykeycoin-tx
    cd ..

Running the daemon:

    anykeycoind 

Stopping the daemon:

    anykeycoin-cli stop

Demon status:

    anykeycoin-cli getinfo
    anykeycoin-cli mnsync status

All binaries for different operating systems, you can download in the releases repository:

https://github.com/technikpto/anykey/releases

P2P port: 27270, RPC port: 27271
-
Distributed under the MIT software license, see the accompanying file COPYING or http://www.opensource.org/licenses/mit-license.php.
