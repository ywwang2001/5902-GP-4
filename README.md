# 5902 Midterm Project – Part 1

Team: **Clara Dragut**, **Yuwen Wang**, **Ziyao Wang**

This repo contains:

- `image_processing.Rmd` — main work
- `data/` — Fashion-MNIST CSVs
- `renv.lock` + `renv/` — package setup
- `ps4.Rproj` — RStudio project

We use **Git** so everyone can:

- work on the same files without emailing
- keep history and undo mistakes
- stay synchronized across machines

---

## FIRST-TIME SETUP (do once per computer)

### 1) Install Git

#### Create a GitHub account

If you do not have one yet:
[https://github.com](https://github.com)

You will need this to upload (push) your work.

#### Get a Personal Access Token (PAT)

This is your password for Git when pushing from the command line.

1. Go here:
   [https://github.com/settings/tokens?type=beta](https://github.com/settings/tokens?type=beta)

2. Click: **“Generate new token”**

3. Give any name (e.g., `R-project`)

4. Select: **repo**

5. Click **Generate**

6. Copy and save the token somewhere safe — you will paste it later when Git asks for a password.

> You will not see the token again after closing the page.

---

#### Install Git (Windows)

1. Download: [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Run installer → keep defaults
3. Make sure Git Bash is included

#### Install Git (macOS)

Open Terminal:

```
xcode-select --install
```

Approve the popup to install Command Line Tools.

---

### 2) Choose a folder and clone the repo

**Windows (Git Bash)**

```
cd ~/Desktop/[your desired path]
```

```
git clone https://github.com/ywwang2001/5902-GP-4.git
```

```
cd 5902-GP-4
```

**macOS (Terminal)**

```
cd ~/Desktop/[your desired path]
```

```
git clone https://github.com/ywwang2001/5902-GP-4.git
```

```
cd 5902-GP-4
```

### 3) Open the project in RStudio

- In RStudio: **File → Open Project…** → select `ps4.Rproj`.

### 4) Install packages using renv

In the **RStudio Console**, copy/paste these **commands line by line**:

```
install.packages("renv")
```

```
renv::restore()
```

This sets up the exact package versions for the project.

---

## DAILY WORKFLOW (every time you work)

1) **Pull the latest changes**

```
git pull
```

2) **Work in RStudio**
- Open `image_processing.Rmd`
- Everyone works on their assigned model section

3) **Save and share your changes**

```
git add .
```

```
git commit -m "Describe what you changed"
```

```
git push
```

---

## USING `renv` (packages & environment)

`renv` ensures everyone uses the same R packages and versions so code runs the same on all machines.

---

### First time opening the project

1. Open `ps4.Rproj` in RStudio.
2. In the Console, run:

```
install.packages("renv")
```

```
renv::restore()
```

This installs the packages specified in `renv.lock`.
Then open `image_processing.Rmd` to begin working.

---

### Every time you start working

1. Pull the latest code:

```
git pull
```

2. Restore the environment:

```
renv::restore()
```

If nothing changed, this completes quickly.
If packages were added/updated by teammates, they will be installed.

Then begin working in RStudio.

---

### If you install a new package

1. Install normally:

```
install.packages("packagename")
```

2. Update the lockfile so others can restore the same version:

```
renv::snapshot()
```

---

### If you remove a package

1. Delete the `library(packagename)` line from the code.
2. Clean unused packages:

```
renv::clean()
```

3. Update the lockfile:

```
renv::snapshot()
```

---

### Other useful commands

List what packages the project uses:

```
renv::dependencies()
```

Check if project environment is synchronized:

```
renv::status()
```

Restore environment (safe to run anytime):

```
renv::restore()
```

## If you do **not** want to use Git

1. Click **Code → Download ZIP** (top-right of this page)

2. Extract the ZIP, open `ps4.Rproj` in RStudio

3. Install and restore packages (once per computer):

```
install.packages("renv")
```

```
renv::restore()
```

4. Edit `image_processing.Rmd` only in **your assigned section**

5. When finished, **email your updated `image_processing.Rmd` to [yw3413@columbia.edu](mailto:yw3413@columbia.edu)**. I will integrate your changes into the main project.

> **Note:**
> This method works, but you lose version-control benefits (history, sync, conflict handling).
> Using Git is strongly recommended so everyone stays up to date automatically.
