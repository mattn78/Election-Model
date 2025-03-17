# Task 0: Laying the Framework
Note that the individual objectives in this task can be completed independently, and in whichever order

*Copy commands using the button provided by Discord, and paste onto terminal with a right click (ctrl + click on mac)*

## Objective 0.1: Set up your programming environment

*First two steps are probably already done if you took CMSC330*

1. **[For Windows only]** Install WSL2: https://learn.microsoft.com/en-us/windows/wsl/install

2. **[For Windows only]** Get a linux distro

3. Open your terminal (WSL for Windows, default for Mac)

4. Install Anaconda
> **[For Windows only]** Run the following commands:
> ```bash
> sudo apt-get update
> sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
> ```
> Then run the following commands:
> ```bash
> mkdir tmp_anaconda
> cd tmp_anaconda
> ```
> **[For Windows only]** Run the following commands:
> ```bash
> curl -O https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh
> bash Anaconda3-2024.02-1-Linux-x86_64.sh
> ```
> **[For MacOS only]** Run the following commands:
> ```bash
> curl -O https://repo.anaconda.com/archive/Anaconda3-2024.02-1-MacOSX-x86_64.sh
> bash Anaconda3-2024.02-1-Linux-x86_64.sh
> ```
> Press Enter to review license agreement, then press and hold Enter to scroll.
> 
> Enter `yes` to agree to the license.
> 
> When prompted for an install path, press Enter to accept the default location
> 
> Enter `yes` when prompted again to update shell profile

5. Refresh your terminal and cleanup
> Run the following commands:
> ```bash
> source ~/.bashrc
> cd ..
> rm -rf tmp_anaconda
> ```

6. Set up conda environment
> Run the following command:
> ```bash
> conda update conda
> ```
> Select yes when prompted
> 
> Run the following command:
> ```bash
> conda create -n sprvs
> ```
> Select yes if prompted
> 
> Run the following commands:
> ```bash
> conda activate sprvs
> conda install python numpy pandas matplotlib scipy scikit-learn seaborn requests tqdm jupyter ipython
> ```
> Select yes when prompted

7. **[Optional but highly recommended]** Set up VSCode
> Install VSCode from the official website
> 
> Open VSCode by running the command `code` in your terminal
> 
> Install the following extensions:
> - Jupyter
> - Jupyter Keymap
> - Jupyter Slide Show
> - Jupyter Cell Tags
> - Jupyter Notebook Renderers
> - Python

## Objective 0.2: Set up our collaborative environment

1. Make a github account and send it to me

2. Set up an SSH key
> Run the command:
> ```bash
> ls ~/.ssh
> ```
> Check if there are two files named `id_ed25519` and `id_ed25519.pub`
> 
> If **not**, run the command
> ```bash
> ssh-keygen -t ed25519 -C "your_email@example.com"
> ```
> Press enter when prompted for file name, so it should use the default file name
> 
> When prompted for a passphrase, enter one if you'd like. I personally don't use one.
> 
> Run the command:
> ```bash
> ssh-add ~/.ssh/id_ed25519
> cat ~/.ssh/id_ed25519.pub
> ```
> Highlight the displayed text, and right click to copy.

3. Add SSH key to your github
> Follow step 2 and on [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).

4. Clone our shared repository
> After you accept my invite to our repo, run the following command:
> ```bash
> git clone git@github.com:Eurcrue/project-supervise.git
> ```

**Each of us has a folder with our initials. Please only edit files in your own folders.** 

Feel free to copy from other people's folders though.

If you really want to practice git, you should make your own branch and merge whenever you push.

### Some useful git commands after you have cloned the first one:
- `git pull`
 - Updates your local copy of the repo
- `git add <filename>`
 - Tells git to keep track of the changes you made to the file
 - `--all` instead of `<filename>` will tell git to keep track of all changes made
- `git commit -m "message about changes`
 - Tells git to save that you've made a new version of the repo
- `git push`
 - Updates the shared copy of the repo

Usually I do these commands in order to save my changes to the shared copy:
```bash
git pull
git add --all
git commit -m "message here"
git push
```

## Objective 0.3: Get acquainted with tools and context

Skim/read the following. The higher they are on the list, the more important they are to understand.

1. https://github.com/albahnsen/ML_RiskManagement/blob/master/notebooks/02-IntroPython_Numpy_Scypy_Pandas.ipynb

2. https://discord.com/channels/1240655841179205694/1243744708895707187/1243748963039969301

3. The Central Limit Theorem. (One or both)
    - https://www.youtube.com/watch?v=rzFX5NWojp0 -> https://www.youtube.com/watch?v=XLCWeSVzHUU -> https://www.youtube.com/watch?v=YAlJCEDH2uY

    - https://www.youtube.com/watch?v=zeJD6dqJ5lo

4. Linear Regression. (Both)
    - https://www.youtube.com/watch?v=yMgFHbjbAW8
    - https://www.youtube.com/watch?v=lng4ZgConCM

5. How other models work. I list them in order of accessibility. We should meet to discuss our model, so this isn't super important.
    - https://2020.polistat.mbhs.edu/methodology/
    - https://fivethirtyeight.com/features/how-fivethirtyeights-2020-presidential-forecast-works-and-whats-different-because-of-covid-19/
    - https://projects.economist.com/us-2020-forecast/president/how-this-works