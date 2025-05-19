name: Generate Snake Game

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      
      - name: Generate Snake
        uses: Platane/snk@master
        with:
          github_user_name: Estheban18
          svg_path: ./output/github-contribution-grid-snake.svg
          
      - name: Push to GitHub
        run: |
          git config --global user.name "Estheban18"
          git config --global user.email "rojaszamoraestheban19@gmail.com"
          git add -A
          git commit -m "Update snake game"
          git push   
