FROM ubuntu:20.04

# Define build-time arguments
ARG DEBIAN_FRONTEND=noninteractive

# Set environment variables
ENV LANG=C.UTF-8 \
    PATH="/usr/local/bin:$PATH"

# Expose typical development ports
EXPOSE 3000 8080

# Install useful CLI tools
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        curl \
        wget \
        git \
        jq \
        make \
        vim \
        kubectl \
        iputils-ping && \
    rm -rf /var/lib/apt/lists/*

# Add a custom script
COPY tools/setup.sh /usr/local/bin/setup.sh
RUN chmod +x /usr/local/bin/setup.sh

# Run the script (demonstrates a shell step)
RUN /usr/local/bin/setup.sh

# Use Heredoc to define multi-line command
RUN bash <<EOF
echo "Installing mytool..."
curl -sL https://example.com/install.sh | bash
EOF

# Final command
CMD ["bash"]
