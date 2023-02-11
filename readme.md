# **League of Legends Auto Reporter**

---

## Table of Contents

- [Description](#description)
- [Technologies Used](#technologies-used)
- [Background](#background)
- [Features](#features)
- [FAQ](#faq)
- [Roadmap](#roadmap)
- [Sponsorship and Funding](#sponsorship-and-funding)

# Description

Ever been caught in the frustrating situation of wanting to report a player for their post-game behavior but feeling like your report doesn't make a difference? Well, worry no more! With this project, I've created a system that not only finalizes player penalties but also accelerates the process, ensuring that justice is served swiftly.

# Technologies Used

### This project created with:

* selenium
* difflib

# Background

I wrote this automation because I realized that the in-game reporting system is not as effective as the special complaint sent to the support unit. Searching and filling in details such as player name, game number, complaint type one by one every time is also a waste of time and the number of toxic players is quite high, I thought it was time to roll up my sleeves.
Trust me, your gaming experience will thank you.

# Features

* First, we search and find the in-game names of the games to complain about on the relevant sites.

```apache
..........

reported_players = ask_reported_players.split(",")
for player in reported_players:
reported_list.append(player)ask_username = input("Lütfen kendi kullanıcı adınızı giriniz: ")
reported_list = []
ask_reported_players = input("Hangi şampiyonları reportlayacaksın: ")

..........

if all(player.lower() in [name.lower() for name in summoner_dict.values()] for player in reported_players):
    for player in reported_players:
        closest_match = difflib.get_close_matches(player, summoner_dict.values(), n=1)[0]
        print("Reportlanacak oyuncu bulundu")
        print("Reportlanacak oyuncu: ", closest_match, "Kullanıcı adı: ",
              list(summoner_dict.keys())[list(summoner_dict.values()).index(closest_match)])
        get_username.append(list(summoner_dict.keys())[list(summoner_dict.values()).index(closest_match)])
```

---

* After the relevant player names are found, we select which type of behavior to report and have the ready-made complaint text selected from the relevant library that has been added.

```apache
.........

report_dict = {
    "sataşma": "Sataşma, çeşitli aşağılamalar ve hakaretler ile takım huzurunu ve benim huzurumu bozmaktadır. Gerekli cezayı alacağına inanıyorum, iyi çalışmalar dilerim.",
    "nefret söylemi": "Kadın cinsiyeti ile organlarını aşağılan, faşist, hadsiz, cinsiyetçi hakaret ve küfürleri ile insan onurunu zedeleyici, aşağılayıcı davranışlarda bulanan oyuncuların gerekli en ağır cezayı alacağına eminim, iyi çalışmalar dilerim"}

ask_report_type = input("Lütfen report tipini (sataşma, nefret söylemi) giriniz: ")
if ask_report_type == "sataşma":
    baslik = "Sataşma, aşağılama"
    aciklama = report_dict["sataşma"]
else:
    baslik = "Nefret söylemi, değerleri zedeleyici söylemler"
    aciklama = report_dict["nefret söylemi"]

..........
```

* In the last part, he automatically logs in to the support unit on the Riot Games website with his username and password and sends the complaint by completing all the specified boxes.

# FAQ

**1. Where is the full code file ?**
I know you're probably wondering why I haven't shared the source file - but trust me, it's for your own good! I don't want any potential violations or abuses to occur, and I'm sure you wouldn't want that either.

* Now, let's talk about the code. While it may not be ultra miraculous (I'm not exactly Tony Stark), it gets the job done. And hey, if someone out there thinks they can print it with ChatGPT, go right ahead! I encourage you to print it out and see for yourself.

**2. How can i reach the program ?**
Imagine a world where your software dreams can become a reality with just a few clicks! Well, I'm happy to announce that dream can now be a reality thanks to my innovative program. However, as much as I'd love to provide this service for free, I'm afraid servers don't run on dreams alone.If you're interested in helping me out, I'll be more than happy to share some exclusive perks with you.

# Roadmap

### For possible improvements:

1. In order for the related screenshots to be added automatically, a folder can be created and the drag-and-drop method can be added to the algorithm.
2. The library can be improved for complaint types, for example, new content can be added for AFK players or intentionally feeding players.

# Sponsorship and Funding

Hello there!

I'm a lone wolf developer who got fed up with the in-game reporting system's inefficiency in handling complaints. I mean, who has time to search and fill in details like player name, game number, and complaint type every time a toxic player ruins the fun? That's why I put my coding skills to work and created this handy automation tool to streamline the reporting process and get rid of those bad apples.

With just a few clicks, you can now easily report these troublemakers to the support unit and get back to the game. No more wasting time filling out pesky complaint forms. This software is a total game-changer and I'm excited to share it with fellow League of Legends enthusiasts.

So why wait? Try out this software and enjoy a more enjoyable and toxic-free gaming experience!"
