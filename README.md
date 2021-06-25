[![API Reference](
https://camo.githubusercontent.com/915b7be44ada53c290eb157634330494ebe3e30a/68747470733a2f2f676f646f632e6f72672f6769746875622e636f6d2f676f6c616e672f6764646f3f7374617475732e737667
)](https://godoc.org/github.com/33cn/chain33)
[![pipeline status](https://api.travis-ci.org/33cn/chain33.svg?branch=master)](https://travis-ci.org/33cn/chain33/)
[![Go Report Card](https://goreportcard.com/badge/github.com/33cn/chain33)](https://goreportcard.com/report/github.com/33cn/chain33)
 [![Windows Build Status](https://ci.appveyor.com/api/projects/status/github/33cn/chain33?svg=true&branch=master&passingText=Windows%20-%20OK&failingText=Windows%20-%20failed&pendingText=Windows%20-%20pending)](https://ci.appveyor.com/project/33cn/chain33)
[![codecov](https://codecov.io/gh/33cn/chain33/branch/master/graph/badge.svg)](https://codecov.io/gh/33cn/chain33) [![Join the chat at https://gitter.im/33cn/Lobby](https://badges.gitter.im/33cn/Lobby.svg)](https://gitter.im/33cn/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


# GXL blockchain development framework (in order to adapt to the version number standard of go module, the latest version number is changed to 1.65.0)

Chain199, a blockchain system independently developed by optical chain, adopts a variety of consensus mechanisms suitable for commercial development, is highly modular, greatly reduces the development and maintenance costs of blockchain, and has many advantages, such as low delay and high throughput. It is suitable for the application of private chain and alliance chain, and quickly realizes the one click carrying of public chain to realize the convenient advantage of chain reform


Official plug-in library：https://github.com/CLASS-CHAIN/plugin
Typical cases of official plug-in library: https://github.com/bityuan/bityuan

## Building from source

Environmental requirements: Go (version 1.13 or later)

compile:

```shell
git clone https://github.com/njbst/GXL.git $GOPATH/src/github.com/njbst/GXL
cd $GOPATH/src/github.com/njbst/GXL
//Domestic users need to import agents
export GOPROXY=https://mirrors.aliyun.com/goproxy
make
```

```
Note: domestic users need to add an alicloud agent to obtain dependency packages. The mod function is enabled by default in makefile
```

Test:

```shell
$ make test
```

## function

With this command, you can run a single node to the environment, which can be used for development and testing

```shell
$ chain33 -f chain33.toml
```
## Contribution code

Let's talk about the detailed process of code contribution first. Users can directly see the simplified process of code contribution without looking at these processes

### Detailed process

* If you have any ideas, set up issues and discuss with us.
* First, click the fork icon in the upper right corner to add GXL fork to your own branch. For example, mine is xxx/GXL
* `git clone https://github.com/xxx/GXL.git $GOPATH/src/github.com/xxx/GXL`

```
be careful:Here you need to clone to $gopath / SRC / github.com/xxx/gxl, otherwise the go package path will not be found
```

* Add to `xxx/GXL` Distal branch： `git remote add upstream https://github.com/xxx/GXL.git`  I've added this to makefile and can run it directly `make addupstream` 

* To keep the 'xxx / GXL' and 'xxx / GXL' master branches synchronized, you can directly run 'make sync', or execute the following command

```
git fetch upstream
git checkout master
git merge upstream/master
```
```
Note: do not modify the master branch. In this way, the master branch will always be synchronized with the upstream / master
```

* Start from the branch of the latest XXX / GXL code

```
git fetch upstream
git checkout master
git merge upstream/master
git branch -b "fixbug_ci"
```

* After development, push to `xxx/gxl`

```
git fetch upstream
git checkout master
git merge upstream/master
git checkout fixbug_ci
git merge master
git push origin fixbug_ci
```

Then pull request is performed on the interface

### Simplify the process

#### Preparation stage

*First, click the fork icon in the upper right corner, GXL fork to your own branch,For example, mine is XXX / GXL
* `git clone https://github.com/xxx/GXL.git $GOPATH/src/github.com/njbst/GXL`

```
Note: you need to clone to $gopath / SRC / github.com/njbst/gxl, otherwise the go package path will not be found
```

```
make addupstream
```

#### Start development: set the branch name by yourself

```
make branch b=mydevbranchname
```

#### Development completed: push 

```
make push b=mydevbranchname  m = "this submitted information"
```

If m is not set, the command git commit will not be executed

## Modify someone else's pull requse

For example, I want to modify the PR of name = libangzhu branch gxl-p2p-listenport

##### Step1: pull the branch to be modified

```
make pull name=libangzhu b=GXL-p2p-listenPort
```

Then modify the code, and after the modification is completed, commit it locally

###### Step 2: push the modified content

```
make pullpush name=libangzhu b=GXL-p2p-listenPort
```

## License

```
BSD 3-Clause License

Copyright (c) 2018, 33.cn
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the copyright holder nor the names of its
  contributors may be used to endorse or promote products derived from
  this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
