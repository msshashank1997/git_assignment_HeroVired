# git_assignment_HeroVired

# Git LFS Integration Guide

This repository demonstrates the usage of Git Large File Storage (LFS) for handling large binary files efficiently.

## Prerequisites

1. Install Git LFS on your system:
   ```bash
   # For macOS (using Homebrew)
   brew install git-lfs

   # For Ubuntu/Debian
   sudo apt-get install git-lfs

   # For Windows (using Chocolatey)
   choco install git-lfs
   ```

## Initial Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/msshashank1997/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   ```

1. List existing tags (optional, to check current tags)

   ```
   git tag
   ```

2. Create a new tag

   ```
   git tag -a v1.0.0 -m "First stable release"
   ```

3. Push the tag to GitHub
   
   ```
   git push origin v1.0.0
   ```
   
2. Create and checkout to the 'lfs' branch:
   ```bash
   git checkout -b lfs
   ```

3. Initialize Git LFS:
   ```bash
   git lfs install
   ```

4. Configure file types to be tracked by Git LFS:
   ```bash
   # Track large binary files (examples)
   git lfs track "*.zip"
   git lfs track "*.iso"
   git lfs track "*.bin"
   ```

5. Add the .gitattributes file:
   ```bash
   git add .gitattributes
   git commit -m "Initialize Git LFS tracking"
   ```

## Adding Large Files

1. Add your large binary files to the repository:
   ```bash
   # The files will automatically be tracked by Git LFS based on the patterns in .gitattributes
   git add your_large_file.zip
   git commit -m "Add large binary file"
   ```

2. Push the changes:
   ```bash
   git push origin lfs
   ```

## Verifying the Setup

1. Clone the repository on another machine:
   ```bash
   git clone https://github.com/msshashank1997/git_assignment_HeroVired.git
   cd git_assignment_HeroVired
   ```

2. Switch to the 'lfs' branch:
   ```bash
   git checkout lfs
   ```

3. Verify that Git LFS is working:
   ```bash
   git lfs ls-files
   ```

## Important Notes

- Large files (>200MB) will be stored using Git LFS
- The actual file content is stored on GitHub's LFS server
- Only pointers to these files are stored in the Git repository
- Files are downloaded automatically when checking out branches
- You can use `git lfs pull` to manually download LFS files

## Troubleshooting

If you encounter issues:

1. Verify Git LFS is installed:
   ```bash
   git lfs version
   ```

2. Check Git LFS configuration:
   ```bash
   git lfs env
   ```

3. Ensure tracking is set up correctly:
   ```bash
   git lfs track
   ```