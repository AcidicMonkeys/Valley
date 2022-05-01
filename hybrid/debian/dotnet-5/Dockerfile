# /////////////////////////////////////////////////////////////////////////// #
#                                                                             #
#                      Copyright 2022 TheH2SO4                                #
#                                                                             #
#   Licensed under the Apache License, Version 2.0 (the 'License');           #
#   you may not use this file except in compliance with the License.          #
#   You may obtain a copy of the License at                                   #
#                                                                             #
#       http://www.apache.org/licenses/LICENSE-2.0                            #
#                                                                             #
#   Unless required by applicable law or agreed to in writing, software       #
#   distributed under the License is distributed on an 'AS IS' BASIS,         #
#   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  #
#   See the License for the specific language governing permissions and       #
#   limitations under the License.                                            #
#                                                                             #
# /////////////////////////////////////////////////////////////////////////// #

# ////////////////| [🥽] | TheH2SO4 | [⚗️] |//////////////// #

# || Debian [🚀]-[Dotnet-5]-[Hybrid] || #

FROM        --platform=$TARGETOS/$TARGETARCH debian:10.11

LABEL       author="TheH2SO4" maintainer="theh2so4@protonmail.com"

RUN         apt-get update -y \
            && apt-get upgrade -y \
            && apt-get install -y wget \
            && wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb \
            && dpkg -i packages-microsoft-prod.deb \
            && apt-get update -y \
            && apt-get install -y dotnet-sdk-5.0 aspnetcore-runtime-5.0 libgdiplus \
            && apt-get install -y gcc g++ libgcc1 lib32gcc1 gdb libc6 git wget curl tar zip unzip binutils xz-utils liblzo2-2 cabextract iproute2 net-tools netcat telnet libatomic1 libsdl1.2debian libsdl2-2.0-0 libfontconfig libicu63 icu-devtools libunwind8 libssl-dev sqlite3 libsqlite3-dev libmariadbclient-dev libduktape203 locales ffmpeg gnupg2 apt-transport-https software-properties-common ca-certificates tzdata \
            && apt-get update -y \
            && apt-get upgrade -y \
            && adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]