# The idea
We tried to come up with an fun and interesting way of fixing errors on Open Street Map (OSM) by adding a gamification layer to a map viewer.

## How it is build?
We used [figma](https://www.figma.com/) to build our prototype and implement our concept of gamification. By this we were able to quickly iterate through different ideas and come up with a solution that is easy to understand and motivates users to improve publicly available map data. 

## What drives the user?
We try to incentivize the user through rewards like experience points and coins. These can be redeemed for virtual skins and cosmetic items that customize the personal avatar. At the same time this allows the user to express his contribution to the overall map data. With special temporary items which can be earned in quests, we try to incentivize the user further. These time limited quests should encourage users to fix more issues but not punish those who do not have time.

## What about the ML part?
We implemented a transfer-learning approach using pre-trained ResNet-18 ([paper](https://arxiv.org/pdf/1512.03385.pdf)). We froze all parameters except those of the last fully-connected layer and retrained the last layer with the images given to use.

# Does it work?
If you want to take a look, please feel free to do so [here](https://www.figma.com/proto/i0o68C89lUCs6UbaKo8hmd/Main?node-id=67%3A686&scaling=scale-down&page-id=0%3A1&starting-point-node-id=1%3A22)

Osmosis out!

# What do all those files do? :thinking:

* `cnn.ipynb`: Jupyter notebook with all the ML stuff
* `models`: state dicts for our two pytorch models
    * `highway1.pth`: No data augmentation
    * `highway2.pth`: Data augmentation with random perspective distortion and rotation
* `results`: CSV output for the OSM issues
    * `output1.csv`: output of classifier 1
    * `output2.csv`: output of classifier 2
    * `extra_output.csv`: output for extra issues (only classifier 1)
* `highway1.txt`: accuracy, precision, and recall of classifier 1 (+ output in human readable format)
* `highway2.txt`: accuracy, precision, and recall of classifier 2 (+ output in human readable format)
