FROM ubuntu:20.04

# Install rbenv dependencies
RUN apt update && apt install -y git curl autoconf bison build-essential \
    libdb-dev libffi-dev libgdbm6 libgdbm-dev libncurses5-dev \
    libreadline6-dev libssl-dev libyaml-dev  zlib1g-dev && rm -rf /var/lib/apt/lists/*

# Add ruby user and switch to it
RUN adduser --gecos '' --disabled-password ruby
USER ruby

# Set paths for rbenv and ruby-build
ENV HOME /home/ruby
ENV PATH $HOME/.rbenv/shims:$HOME/.rbenv/bin:$HOME/.rbenv/plugins/ruby-build/bin:$PATH

# Install rbenv and ruby-build
RUN git clone https://github.com/rbenv/rbenv.git ~/.rbenv
RUN git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

# Install Ruby 2.7.2
RUN rbenv install 2.7.2
RUN rbenv global 2.7.2

# Check ruby version
CMD ruby -v
