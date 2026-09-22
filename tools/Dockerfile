FROM ubuntu:24.04

# Prevent interactive prompts during installation
ENV DEBIAN_FRONTEND=noninteractive

# Install system dependencies
# Ubuntu 24.04 ships Python 3.12, which Bikeshed 6+ requires.
RUN apt-get update && apt-get install -y \
    python3-pip \
    python3-venv \
    python3-pygments \
    texlive-latex-base \
    texlive-latex-recommended \
    texlive-latex-extra \
    texlive-fonts-recommended \
    texlive-fonts-extra \
    texlive-science \
    texlive-extra-utils \
    texlive-pictures \
    texlive-lang-european \
    texlive-luatex \
    texlive-xetex \
    pandoc \
    git \
    curl \
    pkg-config \
    libcairo2-dev \
    libgirepository1.0-dev \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies into a venv (Ubuntu 24.04 marks the system
# Python as externally managed, PEP 668).
#
# Bikeshed is pinned to a major version, not below one: `bikeshed update`
# downloads spec data whose layout tracks the current major release, so an
# old pin plus fresh data breaks the build ("Couldn't find an appropriate
# include file ... given Status 'LD'"). Bump this pin and the base image
# together when Bikeshed 8 lands.
ENV VIRTUAL_ENV=/opt/venv
RUN python3 -m venv "$VIRTUAL_ENV"
ENV PATH="$VIRTUAL_ENV/bin:$PATH"
RUN pip install --upgrade pip && \
    pip install 'bikeshed>=7,<8' jsonschema pydantic[email] requests pycairo

# Initialize Bikeshed spec database (this takes time, so cache it in image)
RUN bikeshed update

# Set working directory
WORKDIR /workspace

# Set non-interactive mode for any future package installations
ENV DEBIAN_FRONTEND=

# Default command
CMD ["/bin/bash"]
