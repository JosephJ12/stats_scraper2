StatsScraper
=============
A simple CLI python web scraper that scrapes NBA
player data from basketball-reference.org and
allows players to be sorted by points, rebounds, and
assists and displayed.

Installation
------------
Save the .py files under Stats-Scraper and run it with python3. See requirements.txt for any module requirements and install them with pip

Or use pip to install stats_scraper directly

::

    pip install stats_scraper

Usage
-----
Code excerpt from __main__.py
::

    from stats_scraper.scraper import Scraper

    scraper = Scraper()

    result = scraper.find_player_by_name("Ivica Zubac")
    print("Printing result\n")
    for p in result:
        print(p)

    sorted_points = scraper.sort_by_points("SG")
    print("========Printing top scorers========\n")
    for scores in sorted_points:
        print(scores[0], scores[1])

    sorted_assists = scraper.sort_by_assists("PF")
    print("\n\n\n=========Printing top 10 assisters========\n")
    count = 0
    for assists in sorted_assists:
        if(count >= 10):
            break
        print(assists[0], assists[1])
        count += 1

    sorted_rebounds = scraper.sort_by_rebounds("PG", "SG")
    print("\n\n\n=========Printing top 20 rebounders========\n")
    count = 0
    for rebounds in sorted_rebounds:
        if(count >= 20):
            break
        print(rebounds[0], rebounds[1])
        count += 1

Acknowledgment
--------------
Thank you to Oscar Sanchez's article "Web Scraping NBA Stats"
for part of the scraping code

License
-------
`MIT
<https://choosealicense.com/licenses/mit/>`_