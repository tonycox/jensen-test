################################################################################
#
# Licensed to the Apache Software Foundation (ASF) under one or more
# contributor license agreements.  See the NOTICE file distributed with
# this work for additional information regarding copyright ownership.
# The ASF licenses this file to You under the Apache License, Version 2.0
# (the "License"); you may not use this file except in compliance with
# the License.  You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM java-base

# install clojure and leiningen
ARG JEPSEN_VERSION=0.1.4
ENV LEIN_ROOT true

ADD https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein /usr/bin
RUN chmod +x /usr/bin/lein

# install jepsen
ADD ./install-jepsen.sh /install-jepsen.sh
RUN chmod a+x /install-jepsen.sh && sh /install-jepsen.sh

# configure ssh
ADD ./init.sh /init.sh
RUN chmod a+x /init.sh

CMD ["sh", "/init.sh"]
