FROM wordpress:latest

RUN apt-get update && apt-get install -y unzip curl && rm -rf /var/lib/apt/lists/*

# Install the plugin
RUN curl -L -o /tmp/plugin.zip https://downloads.wordpress.org/plugin/amazon-s3-and-cloudfront.latest-stable.zip && \
    unzip /tmp/plugin.zip -d /usr/src/wordpress/wp-content/plugins && \
    rm /tmp/plugin.zip

# Copy custom wp-config.php that reads env vars
COPY wp-config.php /usr/src/wordpress/