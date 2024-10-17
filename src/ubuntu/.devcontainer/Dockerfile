FROM buildpack-deps:noble
RUN if id "ubuntu" &>/dev/null; then \
    echo "Deleting user 'ubuntu'" && userdel -f -r ubuntu || echo "Failed to delete ubuntu user"; \  
    else \
    echo "User 'ubuntu' does not exist"; \ 
    fi