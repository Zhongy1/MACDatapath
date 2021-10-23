# MACDatapath

## Setup remote access
Github has removed password authentication in the command line. You will have to set up an ssh key. Follow these steps:
1. Run `ssh-keygen`
2. Navigate to `~/.ssh`
3. Run `cat id_rsa.pub` and copy the output
4. Go to https://github.com/settings/keys
5. Click `New SSH Key`
6. Title it `jumpece`
7. Paste the public key in the Key field
8. Click `Add SSH Key`

## Clone repo
Run `git clone git@github.com:Zhongy1/MACDatapath.git` inside the directory that you want to store the project. The home directory or a directory called 467 would be a valid choice. Avoid moving the project around after cloning to prevent confusing Cadence.

## Library setup
After cloning the repo, you need to tell Cadence where to look for it. Follow these steps:
1. Launch Cadence
2. Go to `Tools > Library Path Editor`
3. In the opened window, go to `View > Include Files`
4. The view should change and a + button appears. Click on that
5. A window appears. Naviagete to MACDatapath, select `cds.lib`, and click open
6. Go to `File > Save`
7. Finally. go to `File > Exit`

## Branches
Everyone will work in their respective exp branches. This will be the way work gets officially saved: `master <- develop <--> dev/* <--> exp/* `
```
master
develop - development branch for saving progress
dev/zhongy1 - dev branches for prepping for merge into develop
dev/rmaddi5
dev/rmedin25
dev/bpoole4
exp/zhongy1 - experimental branches for creating schematics
exp/rmaddi5
exp/rmedin25
exp/bpoole4
```

## File/Folder Structure
Within main, each person has a schematic prepared for them. This is your sandbox for testing experimental components and basic blocks. When components and basic blocks are officially ready, save a copy to the official directories. If there's a bug, modify the experimental copy and then overwrite the official one. Unlike a basic block, a component needs to have all basic block references from the official directory in order to be considered ready.
```
main - circuits that are built from components
  |- zhongy1_exp
  |- rmaddi5_exp
  |- rmedin25_exp
  \- bpoole4_exp
experimental - work in progress components and basic blocks
  |- components
  |    \- *
  \- basic
       \- *
components - official blocks that are built from basic blocks
  \- * - DO NOT MODIFY
basic - official basic blocks like gates
  \- * - DO NOT MODIFY
```