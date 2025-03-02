name: WakaTime Stats

on:
  schedule:
    - cron: '0 0 * * *'
  workflow_dispatch:

jobs:
  update-wakatime:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Update WakaTime Readme Stats
        uses: anmol098/waka-readme-stats@master
        with:
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
          SHOW_TOTAL: "True"
          SHOW_TIMEZONE: "True"
          SHOW_PROFILE_VIEWS: "True"
          SHOW_COMMIT: "True"
          SHOW_DAYS_OF_WEEK: "True"
          SHOW_LANGUAGE: "True"
          SHOW_OS: "True"
          SHOW_PROJECTS: "True"
          SHOW_EDITORS: "True"
