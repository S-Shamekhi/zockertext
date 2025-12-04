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

sudo /tmp/zocker/container/test-container/bin/busybox --install -s /tmp/zocker/container/test-container/bin/
---
sudo rm -rf /tmp/zocker/container/test-container
sudo mkdir -p /tmp/zocker/container/test-container/bin
sudo cp /bin/busybox /tmp/zocker/container/test-container/bin/
sudo chmod +x /tmp/zocker/container/test-container/bin/busybox
sudo /tmp/zocker/container/test-container/bin/busybox --install -s /tmp/zocker/container/test-container/bin/
