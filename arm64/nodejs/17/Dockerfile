#///////////////////////////////////////////////////////////////////////////////////#
#                                                                                   #
#                           Copyright (c) 2021 HiroBeet                             #
#                                                                                   #
#  Permission is hereby granted, free of charge, to any person obtaining a copy     #
#  of this software and associated documentation files (the "Software"), to deal    #
#  in the Software without restriction, including without limitation the rights     #
#  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell        #
#  copies of the Software, and to permit persons to whom the Software is            #
#  furnished to do so, subject to the following conditions:                         #
# --------------------------------------------------------------------------------- #
#  The above copyright notice and this permission notice shall be included in all   #
#  copies or substantial portions of the Software.                                  #
# --------------------------------------------------------------------------------- #
#  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR       #
#  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,         #
#  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE      #
#  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER           #
#  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,    #
#  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE    #
#  SOFTWARE.                                                                        #
#                                                                                   #
#///////////////////////////////////////////////////////////////////////////////////#

#|| NodeJs [17]-[Arm64] ||#

FROM        arm64v8/node:17

LABEL       author="HiroBeet" maintainer="hirobeet@protonmail.com"

RUN         apt update \
            && apt -y install ffmpeg iproute2 git sqlite3 python3 tzdata ca-certificates dnsutils build-essential chromium libcairo2-dev libpango1.0-dev libjpeg-dev libgif-dev librsvg2-dev \
            && npm -g install npm@latest \
            && useradd -m -d /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]