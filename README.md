# Antoni

Antoni is a repository that

## Setup
1. Open VSCode
1. Ensure you have Docker and the Dev Containers extension
1. Reopen in container
1. `rosws update -t src` if you need to initialise the full environment for a new computer
1. `rosdep install --from-paths src`
1. `catkin_make`
1. \[OPTIONAL\] `sudo chown root:video /dev/video*` if you are using any cameras