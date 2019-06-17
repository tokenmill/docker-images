FROM oracle/graalvm-ce:19.0.2
RUN gu install native-image

ENV GRAALVM_HOME=$JAVA_HOME

RUN yum -y install openssh-clients zip
RUN curl -O https://download.clojure.org/install/linux-install-1.10.1.447.sh \
    && chmod +x linux-install-1.10.1.447.sh \
    && ./linux-install-1.10.1.447.sh

CMD clojure -h
