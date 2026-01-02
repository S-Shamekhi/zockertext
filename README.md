

rm -rf /tmp/zocker/exported_root
mkdir -p /tmp/zocker/exported_root
tar -xf export.tar -C /tmp/zocker/exported_root
Step 2 — Show exported root / (Screenshot #1)
ls -la /tmp/zocker/exported_root | head -n 50


📸 Take a screenshot
Label it in your report as:

Exported root filesystem (from export.tar)

Step 3 — Show live container root / (Screenshot #2)
docker exec -it 0e61c8c5c21c sh -c "ls -la / | head -n 50"


📸 Take a screenshot
Label:

Root filesystem inside running container

Step 4 — Compare /proc (MOST IMPORTANT)
Exported /proc (Screenshot #3)
ls -la /tmp/zocker/exported_root/proc | head -n 50


📸 Screenshot
Label:

Exported /proc directory

Live /proc (Screenshot #4)
docker exec -it 0e61c8c5c21c sh -c "ls -la /proc | head -n 50"


📸 Screenshot
Label:

Live /proc directory inside container
----------
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



--------------------------



googledoc to solve the read only 
https://docs.google.com/document/d/1_yn_TIo7Wmo74XUY18KlUCWaMOhPOWRyjgz-GaJKc3g/edit?usp=sharing

