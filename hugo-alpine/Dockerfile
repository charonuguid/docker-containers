FROM golang:1.14.0-alpine
MAINTAINER Charo Nuguid <me@thegeekettespeaketh.com>

# Used for Alpine
RUN apk add --no-cache git
RUN wget https://github.com/gohugoio/hugo/releases/download/v0.65.3/hugo_extended_0.65.3_Linux-64bit.tar.gz \
    && mkdir -p hugo \
    && tar -zxvf hugo_extended_0.65.3_Linux-64bit.tar.gz -C hugo \
    && mv hugo/hugo /go/bin/ \
    && rm -rf hugo*

ARG USERNAME=charo
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
RUN addgroup -g ${USER_GID} -S ${USERNAME} && \
    adduser -u ${USER_GID} -S ${USERNAME} -G ${USERNAME}
#
# Create the user in debian-based os
# RUN groupadd --gid $USER_GID $USERNAME \
#     && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
#
    # && mkdir -p /home/${USERNAME}/.vscode-server /home/${USERNAME}/.vscode-server-insiders \
    # && chown ${USER_UID}:${USER_GID} /home/${USERNAME}/.vscode-server* 
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    # && apt-get update && apt-get install --no-install-reccommends -y sudo \
    # && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    # && chmod 0440 /etc/sudoers.d/$USERNAME

# ********************************************************
# * Anything else you want to do like clean up goes here *
# ********************************************************

# [Optional] Set the default user. Omit if you want to keep the default as root.
# USER ${USERNAME}
