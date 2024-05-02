<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/loccai/loccai/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/loccai/loccai/output/github-contribution-grid-snake.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/loccai/loccai/output/github-contribution-grid-snake.svg">
</picture>

_generated with [Platane/snk](https://github.com/Platane/snk)_

# Visit https://github.com/lowlighter/metrics#-documentation for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          #  - repo
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: LoCCai
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Asia/Shanghai
          plugin_16personalities: yes
          plugin_16personalities_scores: yes
          plugin_16personalities_sections: personality
          plugin_activity: yes
          plugin_activity_days: 14
          plugin_activity_filter: all
          plugin_activity_limit: 5
          plugin_activity_load: 300
          plugin_activity_visibility: all
          plugin_anilist: yes
          plugin_anilist_limit: 2
          plugin_anilist_limit_characters: 22
          plugin_anilist_medias: anime, manga
          plugin_anilist_sections: favorites
          plugin_anilist_shuffle: yes
          plugin_anilist_user: .user.login
          plugin_calendar: yes
          plugin_calendar_limit: 1
          plugin_code: yes
          plugin_code_days: 3
          plugin_code_lines: 12
          plugin_code_load: 400
          plugin_code_visibility: public
          plugin_discussions: yes
          plugin_discussions_categories: yes
          plugin_followup: yes
          plugin_followup_archived: yes
          plugin_followup_sections: repositories
          plugin_habits: yes
          plugin_habits_charts_type: classic
          plugin_habits_days: 14
          plugin_habits_facts: yes
          plugin_habits_from: 200
          plugin_habits_languages_limit: 8
          plugin_habits_languages_threshold: 0%
          plugin_introduction: yes
          plugin_introduction_title: yes
          plugin_lines: yes
          plugin_lines_history_limit: 1
          plugin_lines_repositories_limit: 4
          plugin_lines_sections: base
          plugin_notable: yes
          plugin_notable_from: organization
          plugin_notable_types: commit
          plugin_people: yes
          plugin_people_limit: 24
          plugin_people_size: 28
          plugin_people_types: followers, following
          plugin_poopmap: yes
          plugin_poopmap_days: 7
          plugin_reactions: yes
          plugin_reactions_display: absolute
          plugin_reactions_limit: 200
          plugin_reactions_limit_discussions: 100
          plugin_reactions_limit_discussions_comments: 100
          plugin_reactions_limit_issues: 100
          plugin_stargazers: yes
          plugin_stargazers_charts: yes
          plugin_stargazers_charts_type: graph
          plugin_stargazers_days: 14
          plugin_stargazers_worldmap: yes
          plugin_traffic: yes
