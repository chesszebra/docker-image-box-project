FROM chesszebra/php:7.1

# Run as root
USER root:root

# Configure the system
RUN apt-get update \
 && apt-get install -y --no-install-recommends \
	curl \
	git

# Install box
RUN curl -LSs https://box-project.github.io/box2/installer.php | php \
 && chmod +x box.phar \
 && mv box.phar /usr/local/bin/box

# Run the container as the configured user
USER php:php

# Execute phpunit
ENTRYPOINT ["/usr/local/bin/box"]
