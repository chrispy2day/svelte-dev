FROM node:22-bookworm

LABEL org.opencontainers.image.description="Svelte development container with Node.js 22"
LABEL org.opencontainers.image.source="https://github.com/chrispy2day/svelte-dev"

# Install additional dependencies for Svelte development
RUN npm install -g degit

# Create a non-root user
ARG USERNAME=node
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Ensure node user exists and has correct UID/GID
RUN groupmod --gid $USER_GID $USERNAME \
    && usermod --uid $USER_UID --gid $USER_GID $USERNAME \
    && chown -R $USER_UID:$USER_GID /home/$USERNAME

# Set up workspace
WORKDIR /workspace
RUN chown $USERNAME:$USERNAME /workspace

# Expose Vite default port
EXPOSE 5173
