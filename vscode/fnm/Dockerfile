FROM mcr.microsoft.com/vscode/devcontainers/base:bookworm
RUN apt -y update && \
    apt -y upgrade && \
    apt -y install curl
RUN mkdir /workspaces && \
    chown vscode:vscode /workspaces

USER vscode
ENV FNM_COREPACK_ENABLED=true
RUN curl -fsSL https://fnm.vercel.app/install | bash -s -- --skip-shell --install-dir "/home/vscode/.fnm" && \
    echo 'export PATH="$HOME/.fnm:$PATH"' >> $HOME/.bashrc && \
    echo 'eval "`fnm env --use-on-cd`"' >> $HOME/.bashrc
ENTRYPOINT tail -f /dev/null
