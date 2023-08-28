FROM mcr.microsoft.com/devcontainers/typescript-node:1-18-bullseye

# Install GH CLI
RUN type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)

RUN curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y

# npm and pnpm
RUN npm i -g npm

RUN corepack enable \
&& corepack prepare pnpm@latest --activate