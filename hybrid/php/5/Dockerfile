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

# || PHP [🚀]-[5]-[Hybrid] || #

FROM        --platform=$TARGETOS/$TARGETARCH alpine:latest

LABEL       author="TheH2SO4" maintainer="theh2so4@protonmail.com"

RUN         apk --update --no-cache add ca-certificates \
            && apk add php5 php5-fpm php5-session php5-soap php5-openssl php5-gmp php5-pdo_odbc php5-json php5-dom php5-pdo php5-zip php5-mysqli php5-sqlite3 php5-pdo_pgsql php5-bcmath php5-gd php5-odbc php5-pdo_mysql php5-pdo_sqlite php5-gettext php5-xmlreader php5-bz2 php5-iconv php5-pdo_dblib php5-curl php5-ctype php5-phar php5-fileinfo php5-mbstring php5-tokenizer

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]