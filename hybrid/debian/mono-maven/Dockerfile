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

# || Debian [🚀]-[Mono-Maven-Stable]-[Hybrid] || #

FROM        --platform=$TARGETOS/$TARGETARCH debian:stable

LABEL       author="TheH2SO4" maintainer="theh2so4@protonmail.com"

RUN         apt-get update -y \
            && apt-get upgrade -y \
            && apt-get install -y git ca-certificates iproute2 tzdata apt-transport-https dirmngr gnupg maven \
            && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF \
            && echo "deb http://download.mono-project.com/repo/debian wheezy main" | tee /etc/apt/sources.list.d/mono-xamarin.list \
            && apt-get update -y \
            && apt-get upgrade -y \
            && apt-get install -y mono-complete \
            && apt-get install -y mono-runtime \
            && adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]