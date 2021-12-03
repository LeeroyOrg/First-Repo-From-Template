name: Shell Commands

on: [push]

jobs:
  RunShellCommand:
    name: Run Shell Command
    runs-on: ubuntu-latest

    steps:
      - name: Echo a string
        run: echo "Hello World!!!"

      - name: Echo second string
        run: echo "Awesomeness!!!"

      - name: Echo third string
        run: echo "I'm way cool!!!"

      - name: Multiline script
        run: |
          node -v
          npm -v

      - name: Python command
        run: |
          import os 
          print(os.environ['PATH'])
        shell: python

  RunWindowsCommand:
    name: Run Windows Comamnd
    runs-on: windows-latest
    needs: ["RunShellCommand"]

    steps:
      - name: Get directory using Powershell
        run: Get-Location

      - name: Get directory using Bash
        run: pwd
        shell: bash
