# Alessia8 - basicnodetseslint
An experimental NodeJS project with TypeScript and ESLint.

The accompanying video is
[How to Setup a NodeJS Project with Typescript and ESlint using Visual Studio Code in 2021](https://youtu.be/r-Nzx1T64y4)

The project was setup with these steps:
- npm init to create package.json, set start script as dist/index.js 
- npm install -D typescript ts-node @types/node eslint 
- npx tsc --init to create tsconfig.json and change the settings to your liking 
- **npx eslint --init** to create .eslintrc.json select typescript and node when asked 
    - I made a mistake in the video, when browser and node was asked space bar or *i* had to be used, not the down arrow key. My mistake.
- Install ESlint Visual Studio Code extension, and in the setting for ESLint 
    - Check *Always show the ESLint status bar item* 
    - Select *Problems* for *Code Actions on Save Mode* 
