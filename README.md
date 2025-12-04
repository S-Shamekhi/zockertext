docker inspect b3eee2b4c9dd | jq -r '.[0].GraphDriver.Data.MergedDir'


# Clean and create dir
sudo rm -rf /tmp/zocker/container/test-container
sudo mkdir -p /tmp/zocker/container/test-container/bin

# Copy busybox from your host's /bin (your VM has it)
sudo cp /bin/busybox /tmp/zocker/container/test-container/bin/
sudo chmod +x /tmp/zocker/container/test-container/bin/busybox

# Install symlinks
sudo /tmp/zocker/container/test-container/bin/busybox --install /tmp/zocker/container/test-container/bin

# Go back
cd ~/Downloads/zocker-t3/zocker-t3

If /bin/busybox doesn't exist on your VM, run this instead (uses host sh + libs, but simpler):
sudo mkdir -p /tmp/zocker/container/test-container/{bin,lib,lib64}
sudo cp /bin/sh /tmp/zocker/container/test-container/bin/
sudo cp /lib/x86_64-linux-gnu/libc.so.6 /tmp/zocker/container/test-container/lib/  # adjust if path different
sudo cp /lib/x86_64-linux-gnu/ld-linux-x86-64.so.2 /tmp/zocker/container/test-container/lib/
