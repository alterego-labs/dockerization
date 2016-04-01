# Use official elixir image with latest version at this moment
FROM elixir:1.2.3
MAINTAINER Sergey Gernyak <sergeg1990@gmail.com>

# Set mix environment by default as dev
ENV MIX_ENV=dev

# Install some additional needed system packages
RUN apt-get update && apt-get install -y build-essential git-core

# Create new directory for your application
RUN mkdir -p /app

# Make just created folder as working dir
WORKDIR /app

# Copy all files from the build context to the image.
# Do not forget add `.dockerignore` file with exceptions!
COPY . ./

# Install hex
RUN mix local.hex --force

# Install rebar
RUN mix local.rebar --force

# Install and compile dependencies of your application
RUN mix deps.get && mix deps.compile

# Provide default command for the container
CMD ["iex", "-S", "mix"]
