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

# || Dockerfile [🚀]-[PHP6]-[Hybrid] || #

FROM        --platform=$TARGETOS/$TARGETARCH alpine:latest

LABEL       author="TheH2SO4" maintainer="theh2so4@protonmail.com"

RUN         apk --update --no-cache add ca-certificates nginx \
            && apk add php6 php6-fpm php6-session php6-soap php6-openssl php6-gmp php6-pdo_odbc php6-json php6-dom php6-pdo php6-zip php6-mysqli php6-sqlite3 php6-pdo_pgsql php6-bcmath php6-gd php6-odbc php6-pdo_mysql php6-pdo_sqlite php6-gettext php6-xmlreader php6-bz2 php6-iconv php6-pdo_dblib php6-curl php6-ctype php6-phar php6-fileinfo php6-mbstring php6-tokenizer

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]