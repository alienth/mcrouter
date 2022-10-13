# syntax=docker/dockerfile:1.1-experimental

FROM            ubuntu:focal

ARG MCROUTER_REPO
ENV MCROUTER_REPO=${MCROUTER_REPO:-https://github.com/facebook/mcrouter.git}

# Can be a branch or tag name.
ARG MCROUTER_BRANCH
RUN : "${MCROUTER_BRANCH:?MCROUTER_BRANCH must be set.}"

ENV             MCROUTER_DIR            /usr/local/mcrouter
ENV             DEBIAN_FRONTEND         noninteractive

ENV             PKG_DIR                 $MCROUTER_DIR/pkgs
ENV             INSTALL_DIR             $MCROUTER_DIR/install

RUN             --mount=type=bind,target=/tmp/scripts,source=scripts /tmp/scripts/deps.sh
RUN             --mount=type=bind,target=/tmp/scripts,source=scripts /tmp/scripts/build.sh

ENV             DEBIAN_FRONTEND newt
