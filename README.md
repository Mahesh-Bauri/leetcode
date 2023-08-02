# Creating a Zsh Command for Opening LeetCode Website

In this conversation, we discussed how to create a custom Zsh command to open the LeetCode website, with the ability to specify tags and display help information.

## Overview

We created a custom `leetcode` function in Zsh, allowing users to open the LeetCode website or specific tag pages in their default web browser. The function also provides options for displaying usage instructions and available tags.

## Steps (for MacOS)

1. Open your `~/.zshrc` file for editing:

   ```bash
   nano ~/.zshrc
   ```

2. Add the following `leetcode` function to the file:

```bash
leetcode() {
  if [ "$1" = "-help" ]; then
    echo "Usage: leetcode "
    echo "Opens the LeetCode website in your default browser."
    echo "Options:"
    echo "   array   To open a specific tag page (e.g., array)"
    echo "  -tags   Display a list of available LeetCode tags."
    echo "  -c   To open the LeetCode contest page."
    echo "  -e   To open the LeetCode explore page."
    echo "  -d   To open the LeetCode discussions page."
    echo "  -u username    To open the LeetCode user page (replace username with your username)."
    echo "  -wc contest_number    To open a specific weekly contest page."
    echo "  -bc contest_number    To open a specific biweekly contest page."

  elif [ "$1" = "-tags" ]; then
    echo "Available LeetCode tags:"
    echo "  array"
    echo "  linked-list"
    echo "  tree"
    # Add more tags as needed
  elif [ "$1" = "-c" ]; then
    open "https://leetcode.com/contest"
  elif [ "$1" = "-e" ]; then
    open "https://leetcode.com/explore/"
  elif [ "$1" = "-d" ]; then
    open "https://leetcode.com/discuss"
  elif [ "$1" = "-u" ]; then
    open "https://leetcode.com/$2/"
  elif [ "$1" = "-wc" ]; then
    open "https://leetcode.com/contest/weekly-contest-$2/"
  elif [ "$1" = "-bc" ]; then
    open "https://leetcode.com/contest/biweekly-contest-$2/"
  else
    open "https://leetcode.com/tag/$1"
  fi
}
```

1. Save and exit the text editor.

2. Restart your terminal or run source ~/.zshrc for the changes to take effect.

## Usage

- To open the LeetCode website:

  ```powershell
  leetcode
  ```

- To open the LeetCode explore page:

  ```powershell
  leetcode -e
  ```

- To open the LeetCode contest page:

  ```powershell
  leetcode -c
  ```

- To open the LeetCode discussions page:

  ```powershell
  leetcode -d
  ```

- To open the LeetCode user page (replace `USERNAME` with your username):

  ```powershell
  leetcode -u USERNAME
  ```

- To open a specific weekly contest page (replace `CONTEST_NUMBER` with the contest number):

  ```powershell
  leetcode -wc CONTEST_NUMBER
  ```

- To open a specific biweekly contest page (replace `CONTEST_NUMBER` with the contest number):

  ```powershell
  leetcode -bc CONTEST_NUMBER
  ```

- To open the LeetCode website for a specific tag (e.g., "array"):

  ```powershell
  leetcode array
  ```

- To display available LeetCode tags:

  ```powershell
  leetcode -tags
  ```

- To display usage instructions and options:

  ```powershell
  leetcode -help
  ```

## Customization

You can modify the `leetcode` function by adding more tags to the list or making other adjustments to suit your preferences.

---

# Creating a Custom PowerShell Command for Opening LeetCode Website

In this guide, we'll walk through the process of creating a custom PowerShell command to open the LeetCode website, with the ability to specify tags and display help information.

## Overview

We will create a custom `leetcode` function in PowerShell, which will allow us to open the LeetCode website or specific tag pages in the default web browser. This function will also provide options for displaying usage instructions and available tags.

## Steps (For Windows)

**1. Open your PowerShell profile for editing:**

Open PowerShell and enter the following command to open your PowerShell profile in a text editor:

```powershell
notepad $PROFILE
```

**2. Add the leetcode function:**

Copy and paste the following `leetcode` function into your PowerShell profile file:

```powershell
function leetcode {
    param(
        [string]$Arg1,
        [string]$Arg2
    )

    if ($Arg1 -eq "-help") {

        Write-Output "Usage: leetcode "
        Write-Output "Opens the LeetCode website in your default browser."
        Write-Output "Options:"
        Write-Output "   array   To open a specific tag page (e.g., array)"
        Write-Output "  -tags   Display a list of available LeetCode tags."
        Write-Output "  -c   To open the LeetCode contest page"
        Write-Output "  -e   To open the LeetCode explore page:"
        Write-Output "  -d   To open the LeetCode discussions page"
        Write-Output "  -u USERNAME    To open the LeetCode user page (replace `USERNAME` with your username)"
        Write-Output "  -wc CONTEST_NUMBER    To open a specific weekly contest page (replace `CONTEST_NUMBER` with the contest number)"
        Write-Output "  -bc CONTEST_NUMBER    To open a specific biweekly contest page (replace `CONTEST_NUMBER` with the contest number)"


    }
    elseif ($Arg1 -eq "-tags") {
        Write-Output "Available LeetCode tags:"
        Write-Output " array"
        Write-Output " backtracking"
        # Add more tags as needed
    }
    elseif ([string]::IsNullOrWhiteSpace($Arg1)) {
        Start-Process "https://leetcode.com"
    }
    elseif ($Arg1 -eq "-c") {
        Start-Process "https://leetcode.com/contest"
    }
    elseif ($Arg1 -eq "-e") {
        Start-Process "https://leetcode.com/explore/"
    }
    elseif ($Arg1 -eq "-d") {
        Start-Process "https://leetcode.com/discuss"
    }
    elseif ($Arg1 -eq "-u") {
        Start-Process "https://leetcode.com/$Arg2/"
    }
    elseif ($Arg1 -eq "-wc") {
        Start-Process "https://leetcode.com/contest/weekly-contest-$Arg2/"
    }
    elseif ($Arg1 -eq "-bc") {
        Start-Process "https://leetcode.com/contest/biweekly-contest-$Arg2/"
    }
    else {
        Start-Process "https://leetcode.com/tag/$Arg1"
    }
}

```

Save the file and close the text editor.

**3. Apply the changes:**

Restart your PowerShell session for the changes to take effect.

## Usage

Now that you've set up the `leetcode` function, you can use it to open the LeetCode website and specific tag pages:

- To open the LeetCode website:

  ```powershell
  leetcode
  ```

- To open the LeetCode explore page:

  ```powershell
  leetcode -e
  ```

- To open the LeetCode contest page:

  ```powershell
  leetcode -c
  ```

- To open the LeetCode discussions page:

  ```powershell
  leetcode -d
  ```

- To open the LeetCode user page (replace `USERNAME` with your username):

  ```powershell
  leetcode -u USERNAME
  ```

- To open a specific weekly contest page (replace `CONTEST_NUMBER` with the contest number):

  ```powershell
  leetcode -wc CONTEST_NUMBER
  ```

- To open a specific biweekly contest page (replace `CONTEST_NUMBER` with the contest number):

  ```powershell
  leetcode -bc CONTEST_NUMBER
  ```

- To open the LeetCode website for a specific tag (e.g., "array"):

  ```powershell
  leetcode array
  ```

- To display available LeetCode tags:

  ```powershell
  leetcode -tags
  ```

- To display usage instructions and options:

  ```powershell
  leetcode -help
  ```
