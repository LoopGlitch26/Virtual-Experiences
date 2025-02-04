### Typically, traders monitor stock prices and trading strategies by having data displayed visually on their screens in chart form. Often these charts will be accompanied by alerts that notify users when certain events occur or when preset price thresholds are hit.

## Step 1: Setup Dev Environment to use JPMC frameworks

  i) `git clone https://github.com/insidesherpa/JPMC-tech-task-2-PY3.git`
  
  ii) Get into the directory and run `python3 datafeed/server3.py`
  
      Output: HTTP server started on port 8080

  iii) Inside Source Code directory, install `npm` by `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash` and then 
  ```
 export NVM_DIR="$HOME/.nvm"
 [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

  iv) Check `nvm --version` == `0.38.0`
  
  v) Install the right npm version `nvm install v11.0.0` and use `nvm use v11.0.0`
  
  node and npm version:
  
  ```
  (base) loopglitch@Not-A-MacBook ~ % node -v
  v11.0.0
  (base) loopglitch@Not-A-MacBook ~ % npm -v
  6.4.1
  ```
  
  vi) `npm install` and `npm start` 
  
  I was facing some issues with my node installation, so my results were like this:
  ![Screenshot 2021-04-29 at 3 33 06 PM](https://user-images.githubusercontent.com/53336715/116534578-8d5ad380-a897-11eb-83a5-5e62ea9583d1.png)
  
  But after doing some fucking troubleshooting, this is the result:![Screenshot 2021-04-29 at 3 56 04 PM](https://user-images.githubusercontent.com/53336715/116537299-e710cd00-a89a-11eb-9c66-b47f9dcf8426.png)

  And this is the working app: ![Screenshot 2021-04-29 at 3 57 23 PM](https://user-images.githubusercontent.com/53336715/116537348-f6901600-a89a-11eb-85ef-866745fcfa36.png)

  Troubleshooting steps: I had to delete the source code `node_modules` and then followed [this](https://github.com/insidesherpa/JPMC-tech-task-2/issues/24#issuecomment-623924068)
  
## Step 2: Making changes

  There are two things we have to achieve here to complete this task

  (1) Make the graph continuously update instead of having to click it a
bunch of times. Also the kind of graph we want to serve as visual here is
kind of a continuously updating line graph whose y axis is the stock’s
top_ask_price and the x-axis is the timestamp of the stock

  (2) Remove / disregard the duplicated data we saw earlier…
  
  Here are the commits with changes [1](https://github.com/LoopGlitch26/Virtual-Experiences/commit/ddebe22faf7b4743510949bf1b0d27aa615adaa5#diff-b54d1f0322ee38c5058bfc45588180e817203dea9bdc8a1ef7bf2ab6262be443) and [2](https://github.com/LoopGlitch26/Virtual-Experiences/commit/4dd850ea06cfce56991e66e7b3ab6f3e092eb74b#diff-b54d1f0322ee38c5058bfc45588180e817203dea9bdc8a1ef7bf2ab6262be443)

![Screenshot 2021-04-29 at 8 46 49 PM](https://user-images.githubusercontent.com/53336715/116575237-500c3b00-a8c3-11eb-88ac-fcd3eeb81e88.png)

Here's the [Patch File](https://github.com/LoopGlitch26/Virtual-Experiences/blob/main/JPMC/JPMC-tech-task-2-PY3/0001-Create-Patch-File.patch)


![Screenshot 2021-04-29 at 8 51 57 PM](https://user-images.githubusercontent.com/53336715/116577851-b42ffe80-a8c5-11eb-8bb4-ff3580479ccb.png)
