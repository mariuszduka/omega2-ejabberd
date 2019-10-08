# XMPP (Jabber) server for Omega2

ejabberd version: **2.1.13**

## About ejabberd

**ejabberd** is a distributed, fault-tolerant technology that allows the creation of large-scale instant messaging applications. The server can reliably support thousands of simultaneous users on a single node and has been designed to provide exceptional standards of fault tolerance. As an open source technology, based on industry-standards, ejabberd can be used to build bespoke solutions very cost effectively.

ejabberd is released under the [GNU General Public License, version 2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html).

## Requirements

Please install first [Erlang/OTP for Omega2](https://github.com/mariuszduka/omega2-erlang)

## Installation

Download the repo:
```
git clone https://github.com/mariuszduka/omega2-ejabberd.git
```

and install package:
```
opkg install omega2-ejabberd/mipsel_24kc/ejabberd_2.1.13_mipsel_24kc.ipk
```

Done!

## Configuration

Modify the file `inetrc` in the directory `/usr/local/ejabberd/etc/ejabberd`:
```
{lookup,["file","native"]}.
{host,{127,0,0,1}, ["localhost","omega-XXXX.local"]}.
{file, resolv, "/etc/resolv.conf"}.
```

Exchange **XXXX** for your Omega2 last 4 digits mac address.

## Usage

You can use the `ejabberdctl` command line administration script to start and stop ejabberd.  
For example:
```
ejabberdctl start
```

Create **admin account**:
```
ejabberdctl register admin localhost password
```

To access **Web Admin** open in your favorite browser the url `http://omega-XXXX.local:5280/admin/`, changing **XXXX** with your device last 4 digits mac address. 

See also [XMPP (Jabber) console client for Omega2](https://github.com/mariuszduka/omega2-mcabber)

## Resources

 * [ejabberd official homepage](https://www.ejabberd.im/)
 * [ejabberd on Github](https://github.com/processone/ejabberd)

## License

MIT License

Copyright (c) 2019 Mariusz Duka

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.