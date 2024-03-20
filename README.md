# Zmod-Metrics
Backup of my edits to Zmod Simply Love Theme for ITG Mania

### About
I was prompted to make this when I got tired of the folder names being centered on the wheel. It made it more difficult to find what I wanted because all of the names were different lengths. It created a very syncopated feel on the wheel for me. For a long time, I've wanted a way to differentiate between stamina and technical packs. Unfortunately, there is no way to really do this through folders, so I opted into at first by changing the names of folders and adding a specific naming convention for me to tell the difference while scrolling. This worked for a good while, but ultimately I still ended up scrolling too far because im braindead. I decided I wanted to dig deeper in how to modify my simply love because I really admire all the work that Zarzob and Zankoku and the many others have put into it which sparked my interest and intrigue. I figured out how to add color based on pack names and this is the result of that. Thanks to Zankoku and Zarzob for some tips on how to get this all working.

## Main Edits
- Left Aligns all song wheel items.
### Code
```lua
SectionExpandedOnCommand=horizalign,left;x,50;maxwidth,WideScale(240,310)
SectionCollapsedOnCommand=horizalign,left;x,50;maxwidth,WideScale(240,310)
```
- Allow for color coded folder/pack names on the song wheel based on type. Using a local list inside of the SectionCollapsedSetCommand.
### Code
```lua
SectionCollapsedSetCommand=%function(self) DiffuseEmojis(self) self:diffuse(1,1,1,1) \
local streamPacks = {"Cathardio", "Arc Stream Works - Mission Mode", "Kyypakkaus 3", "SX14", "SX18", "MWOK's Stream Pack", "Big Bag 3", "Psytrance Division 1", "Arc Stream Works", "Sunday Night Streamin'", "Squirrel Metal II", "Posty", "Posty (Mirror)", "I wish it were always midnight", "Xynn's Inferno", "Sefirot'S SimfileS 5", "pack of charts", "EDW Sound Team \"Σ\"", "BangerZ 3", "Psytrance Division 2", "Classical Classics", "StarryPop Pt. 1", "Shit", "The Starter Pack of Stamina 2", "Big Wong", "69 Bayard", "Chase'ing' The Pack 3", "Delins Incredibly Cool Content", "VGMixtape", "BIGSTAMINA SHARPNEL", "Theoretical touhou", "Jubeat fof", "Linkin Pack", "tyler.ini", "Hospitality Hotfix", "Stamina Secret Santa 2023", "Kyypakkaus 2.5", "SiIvaStreams", "Kyypakkaus 2", "The Joy of Streaming 2", "Stam Snack Pack", "Unbuild of Sharpnel", "HISA Sim v5", "MetaJawnz", "vocaloid is hard 2", "fof no Kirby 64", "Dingoshi Ramen 2", "Dingoshi Ramen 3 Arch", "Chase'ing' The Pack 2.5", "SPAM TOONS 2", "Feelin' Rusty 4", "Xynn's Mix Tapes", "donk is hard", "Hard 2", "nebi time", "The Kellection 2", "tyler.exe", "Manwich's Stream to Midnight", "vocaloid is fast", "PUYO STREAMS 2", "Stamina Secret Santa 2022", "weeb.exe", "Joy of Streaming", "chimichungus", "vocaloid is hard", "Eurobeat Is Fantastic - Second Stage", "Enjou Stamina Package", "Gym Intervals", "the", "Short Snack Simfiles", "Lindsey Stirling", "Mango's Microrave Samplur", "Enjej Stamina Pack", "Simfile Torah", "Braeden's DDR Dumps", "DDRStream Post Supernova", "selected yutsi works", "Stam Cell Research", "touhou is hard", "barbecue lin's $5 pack of stamtech shit", "Stamina Showcase 3 Qualifiers", "Dampstream Full", "big bag", "Hard", "ExJam09 Jams 2", "epic", "yutsi B-sides", "Stamina Alley Part 1 (of 6)", "Zaniel's Junts 2", "selected yutsi works vol. 2", "MONEY MiNiPACK", "Saitama's Ultimate Weapon", "Saitama's Starter Weapon", "Tachyon Lite", "Hardbass Madness 2", "CHASE'ING' THE PACK 2", "MASNA BIEŻNIA", "Stamina Showcase 3", "fofmas 2 but its actually the finished version and not the 16 different half done folders i have on my computer for some reason", "Sick Music for stamina", "Bigger Waves", "Stamina Secret Santa 2021", "Sefirot'S SimfileS 3", "Africa Coast Stamina 1.0", "BeaTrance", "HISA Sim v3", "ExJam09 Jams", "Jayrocking", "Gloryhammer", "fsorae's fstamina ffuckeronis", "DJ Myosuke", "The Starter Pack of Stamina", "Gram Requiem", "BaguetteStreamz 2.5", "Hiiro's Metal Streamz", "Zaniel's Junts", "Jimmy Jawns 4", "Takamachi Walk - wither", "Enjoy Stamina Pack", "Slav Streamz", "Slipstreams", "Skittles Stream Collection", "HISA Sim v4", "Jynx Does Streaming", "yutsi's bass dumpz", "brakecore", "Bass Chasers", "Noah", "PANIKOx II", "138 Is Great", "Kyypakkaus", "Dark Psychungus", "Pendulum Act III", "RGM Extended", "Rhapsody Suites", "ITGAlex's Stamina Singles ep.1", "Goreshit 2020", "itg! Rhythm is just a step away", "fof 2", "Stamina Secret Santa 2020", "yutsi-type beats", "kelly's sm0l stamina pack", "ITGAlex's Stamina Safari", "StoryTime Chapter 1", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "Xynn's LVTS 2", "Euphoreyja", "Demetori ACT I", "Hardbass Madness", "a_hisa stamina v0", "Ch!pzanity", "Petriform's Factory", "StreamVoltex ep.2", "HISA Sim v2", "SlowStreamz", "Resistance Device", "The Kellection", "Dingoshi Ramen", "Stamina Secret Santa 2019", "TranceMania", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "Scrapyard Kent", "Loak STREaMS II", "Lama Freeform Pack 2018", "Death Grips", "Hospitality", "ElEson and Carmelo Minipack", "In The Dump", "Trails of Cold Stream III", "BangerZ 2", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Stamina Showcase 2", "Dampstream 2", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Getty", "Parole Violation", "DimersDozen", "Cuties Party", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Eurobeat Is Fantastic", "FusionStreamz", "can't spell 'christmas' without 'stam'", "Stamina RPG", "Chipzanity", "ECS", "Girls Coast Stamina", "Helblinde", "Pendulum", "Freyja's Grimoire"} \
local technicalPacks = {"Mute Sims X2", "Fred Figglehorn Christmas Minipack", "beat & flow", "Highflyer's Tech Trails 3", "global namespace ~callback~", "zib's hip Hop", "New Years' Stepfile Feast 2023/24", "scryptstagram", "C's Mildly Malevolent Files", "kindly produce a sound", "Rakkii's Raving Records", "9guys1pack", "Hardstyle Goes Hard", "Lovely Techs 5", "Fanatik's Fantastic Pack: Bravery", "XMOD Spectrum", "Hunter's Pack", "Highflyer's Tech-nically Romantic 2", "Shpadoinkle's TECHSTERITY", "Fanatik's Fantastic Pack of LOOOOVE", "Simply Momo & Friends Episode 1", "Kingly's Excellent Mix 5", "Lemonade (updated April 01 2023)", "Technical Proficiency Exam 2", "Valex Sims 2023", "val's minigrinds: vicious", "val's minigrinds (gec heavy charts)", "Eventual Ascension", "ITG Level Asian", "ITG Level Asian Your Smile lowers patch", "gielinor sounds", "Maractus Package", "Shut Up and Take My Money, Benpai", "Summer Vibes Vol. 2", "7gays1pack", "7gays1pack mods patch", "Tech-Bit Adventures", "DieAtic", "Orcacore", "Neo Wax Bloom", "Star Tech The Next Generation", "global namespace 3", "Zaia's Dance Dance Rebuild", "Tev's New Pack of Simfiles 1", "DRILLBOT HITECH", "Braeden's Technicality 2", "PandemiXium Crystal Gazer", "PandemiXium Masterpiece", "PandemiXium Weather Report", "Pandemonium X Presents Wave Ravers", "Pandemonium X Presents Nightfall", "GG Nebulous", "GG Quarantine", "GG Basics", "Bad Stepmaniacs", "Bad Stepmaniacs 2", "Maxx Simz #1", "Valex Sims 2023", "Highflyer's Tech Trails - Korean Air (with BGA videos)", "Highflyer's Tech Trails - Korean Air (videoless)", "The Longest Day", "global namespace 3 ~kernel mode~", "zib's sons", "Bass Tester Extreme", "Zaia's Dance Dance Rebuild + Expansion 1", "Lumi's Lighthouse 2", "Highflyer's Memories of Summer", "Bite-Sized Bangers", "TECH Spectrum", "val's grinds 1", "TakTek 2", "Eventual Ascension 2", "Tech-Bit Adventures 2", "zib's hip Hop", "who asked", "Getting Higgy With It", "dimocracy 3: raucous caucus", "Barber Cuts 3", "Egg Carton", "Kerpa's Simfiles Collab Pack #2", "Technical Deficiency Exam 2", "Horniest Pack in the World", "BPM (Bangerz Per Minute)", "Shpadoinkle's Techsterity #2", "Watch Out Kigha", "Zingers Exclusively", "Tech Heavy Charts (THC)", "Siriusmo Stepped", "Sky's Birthmas", "Secret Stepfile Santa 2023", "Steps of Kivotos Vol. 1: Abydos Shuffle", "sodium chloride vol. 1", "Legendz", "Kou!", "Valex Sims 2022", "7guys1pack", "Shpadoinkle #10", "Highflyer's Tech-nically Romantic", "Bass Tester Extreme", "sorae's stax", "WRSW'S WHIRLWIND", "skittles prime", "Highflyer's Tech Trails 2", "Bangers Only 3", "Hellkite's Tech-ology 1", "dimocracy 2021: second term", "Summer Vibes Vol. 1", "Lovely Techs 4", "Lovely Techs 4 (null offset)", "Kingly's Excellent Mix 4", "Fanatik's Fantastic Pack: Ascension!", "Kawaii-nesis 2", "Tak's Meta Steps (ITG Version)", "Kerpa's Simfiles Playlist 3", "Highflyer's Technically Terrifying (no BG videos)", "Highflyer's Technically Terrifying (yes BG videos)", "ULTRA PARTY MIXTAPES", "C's Meticulously Masochistic Files", "Braeden's Technicality", "Polyphia", "Koreyja 3.5", "Kangaroo Crossover", "Secret Stepfile Santa 2022", "Animal Crossover", "global namespace 2", "Prickly Pear's Poppin' Pack (Full)", "Technical Double Showcase", "Kingly's Excellent Mix 2", "Kerpa's Simfile Playlist 2", "LovelyTechs 3.1", "Resonant Earth", "Rakkii's Extra Cool Tech ANGLES", "TakTek", "Bangers Only 2", "Highflyer's Tech Trails", "Takao's Cherry Blossoms", "Kingly's Excellent Mix 3", "Star Tech", "Super Skittles Selection Turbo", "Secret Stepfile Santa 2021", "Kerpa's Simfiles Collab Pack", "Valex Sims 2021", "dimo's -VI- selifmis", "Rikame's Simfiles 7", "BemaniBeats 6", "Loodee Simfiles 2", "DVogan's Tech Support 3", "Shane's Steps", "Merge", "StoryTime Chapter 1.5", "Kerpa's Simfile Playlist", "global namespace", "Lovely Techs 2", "Skittles Selection 8", "Postmodern Technology", "FrankenFILE", "Mojo's Bizarre Tablature", "Valex Sims 2020", "Shpadoinkle #9", "Bangers Only", "Sudziosis 5.5", "dimo's -V- selifmis", "dimocracy", "jelly down the stream", "Rikame's Simfiles 6", "N.E.O. SiMS 2", "Loak's Inferno", "Silverlution", "5Guys1Pack", "Lovely Techs", "Skittles Selection 7", "Oops! All Tricks!", "CND9's Belligerent Charts", "Notice Me Benpai 2", "Kigha's Best of Both Worlds", "ITGAlex's Compilation 4", "Kacpi is _underjoyed", "Not Even Remotely Poppy", "Barely Playable", "Fraxtil's Monstercat Minipack", "DVogan's Tech Support 2", "SwageSteps 2", "Feraligatr Scales 3", "Chicago Timing Authority", "TYLR's Technical Difficulties", "BemaniBeats 5", "FA and Chill 2", "DVogan's Tech Support", "Lots of Snazzy Simfiles", "BemaniBeats Rev", "Notice Me Benpai", "N.E.O SiMS", "3guys1pack", "ITL"} \
 for packname in ivalues(streamPacks) do \
  if string.find(self:GetText(), packname, 1, true) then self:diffuse(color("#FF2626")) self:shadowlengthx(0) self:shadowlengthy(1) self:shadowcolor(0,0,0,1) end \
 end \
 for packname in ivalues(technicalPacks) do \
  if string.find(self:GetText(), packname, 1, true) then self:diffuse(color("#54b9ff")) self:shadowlengthx(0) self:shadowlengthy(1) self:shadowcolor(0,0,0,1) end \
 end \
end
SectionExpandedSetCommand=%function(self) DiffuseEmojis(self) self:diffuse(1,1,1,1) \
local streamPacks = {"Cathardio", "Arc Stream Works - Mission Mode", "Kyypakkaus 3", "SX14", "SX18", "MWOK's Stream Pack", "Big Bag 3", "Psytrance Division 1", "Arc Stream Works", "Sunday Night Streamin'", "Squirrel Metal II", "Posty", "Posty (Mirror)", "I wish it were always midnight", "Xynn's Inferno", "Sefirot'S SimfileS 5", "pack of charts", "EDW Sound Team \"Σ\"", "BangerZ 3", "Psytrance Division 2", "Classical Classics", "StarryPop Pt. 1", "Shit", "The Starter Pack of Stamina 2", "Big Wong", "69 Bayard", "Chase'ing' The Pack 3", "Delins Incredibly Cool Content", "VGMixtape", "BIGSTAMINA SHARPNEL", "Theoretical touhou", "Jubeat fof", "Linkin Pack", "tyler.ini", "Hospitality Hotfix", "Stamina Secret Santa 2023", "Kyypakkaus 2.5", "SiIvaStreams", "Kyypakkaus 2", "The Joy of Streaming 2", "Stam Snack Pack", "Unbuild of Sharpnel", "HISA Sim v5", "MetaJawnz", "vocaloid is hard 2", "fof no Kirby 64", "Dingoshi Ramen 2", "Dingoshi Ramen 3 Arch", "Chase'ing' The Pack 2.5", "SPAM TOONS 2", "Feelin' Rusty 4", "Xynn's Mix Tapes", "donk is hard", "Hard 2", "nebi time", "The Kellection 2", "tyler.exe", "Manwich's Stream to Midnight", "vocaloid is fast", "PUYO STREAMS 2", "Stamina Secret Santa 2022", "weeb.exe", "Joy of Streaming", "chimichungus", "vocaloid is hard", "Eurobeat Is Fantastic - Second Stage", "Enjou Stamina Package", "Gym Intervals", "the", "Short Snack Simfiles", "Lindsey Stirling", "Mango's Microrave Samplur", "Enjej Stamina Pack", "Simfile Torah", "Braeden's DDR Dumps", "DDRStream Post Supernova", "selected yutsi works", "Stam Cell Research", "touhou is hard", "barbecue lin's $5 pack of stamtech shit", "Stamina Showcase 3 Qualifiers", "Dampstream Full", "big bag", "Hard", "ExJam09 Jams 2", "epic", "yutsi B-sides", "Stamina Alley Part 1 (of 6)", "Zaniel's Junts 2", "selected yutsi works vol. 2", "MONEY MiNiPACK", "Saitama's Ultimate Weapon", "Saitama's Starter Weapon", "Tachyon Lite", "Hardbass Madness 2", "CHASE'ING' THE PACK 2", "MASNA BIEŻNIA", "Stamina Showcase 3", "fofmas 2 but its actually the finished version and not the 16 different half done folders i have on my computer for some reason", "Sick Music for stamina", "Bigger Waves", "Stamina Secret Santa 2021", "Sefirot'S SimfileS 3", "Africa Coast Stamina 1.0", "BeaTrance", "HISA Sim v3", "ExJam09 Jams", "Jayrocking", "Gloryhammer", "fsorae's fstamina ffuckeronis", "DJ Myosuke", "The Starter Pack of Stamina", "Gram Requiem", "BaguetteStreamz 2.5", "Hiiro's Metal Streamz", "Zaniel's Junts", "Jimmy Jawns 4", "Takamachi Walk - wither", "Enjoy Stamina Pack", "Slav Streamz", "Slipstreams", "Skittles Stream Collection", "HISA Sim v4", "Jynx Does Streaming", "yutsi's bass dumpz", "brakecore", "Bass Chasers", "Noah", "PANIKOx II", "138 Is Great", "Kyypakkaus", "Dark Psychungus", "Pendulum Act III", "RGM Extended", "Rhapsody Suites", "ITGAlex's Stamina Singles ep.1", "Goreshit 2020", "itg! Rhythm is just a step away", "fof 2", "Stamina Secret Santa 2020", "yutsi-type beats", "kelly's sm0l stamina pack", "ITGAlex's Stamina Safari", "StoryTime Chapter 1", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "Xynn's LVTS 2", "Euphoreyja", "Demetori ACT I", "Hardbass Madness", "a_hisa stamina v0", "Ch!pzanity", "Petriform's Factory", "StreamVoltex ep.2", "HISA Sim v2", "SlowStreamz", "Resistance Device", "The Kellection", "Dingoshi Ramen", "Stamina Secret Santa 2019", "TranceMania", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "Scrapyard Kent", "Loak STREaMS II", "Lama Freeform Pack 2018", "Death Grips", "Hospitality", "ElEson and Carmelo Minipack", "In The Dump", "Trails of Cold Stream III", "BangerZ 2", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Stamina Showcase 2", "Dampstream 2", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Getty", "Parole Violation", "DimersDozen", "Cuties Party", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Eurobeat Is Fantastic", "FusionStreamz", "can't spell 'christmas' without 'stam'", "Stamina RPG", "Chipzanity", "ECS", "Girls Coast Stamina", "Helblinde", "Pendulum", "Freyja's Grimoire"} \
local technicalPacks = {"Mute Sims X2", "Fred Figglehorn Christmas Minipack", "beat & flow", "Highflyer's Tech Trails 3", "global namespace ~callback~", "zib's hip Hop", "New Years' Stepfile Feast 2023/24", "scryptstagram", "C's Mildly Malevolent Files", "kindly produce a sound", "Rakkii's Raving Records", "9guys1pack", "Hardstyle Goes Hard", "Lovely Techs 5", "Fanatik's Fantastic Pack: Bravery", "XMOD Spectrum", "Hunter's Pack", "Highflyer's Tech-nically Romantic 2", "Shpadoinkle's TECHSTERITY", "Fanatik's Fantastic Pack of LOOOOVE", "Simply Momo & Friends Episode 1", "Kingly's Excellent Mix 5", "Lemonade (updated April 01 2023)", "Technical Proficiency Exam 2", "Valex Sims 2023", "val's minigrinds: vicious", "val's minigrinds (gec heavy charts)", "Eventual Ascension", "ITG Level Asian", "ITG Level Asian Your Smile lowers patch", "gielinor sounds", "Maractus Package", "Shut Up and Take My Money, Benpai", "Summer Vibes Vol. 2", "7gays1pack", "7gays1pack mods patch", "Tech-Bit Adventures", "DieAtic", "Orcacore", "Neo Wax Bloom", "Star Tech The Next Generation", "global namespace 3", "Zaia's Dance Dance Rebuild", "Tev's New Pack of Simfiles 1", "DRILLBOT HITECH", "Braeden's Technicality 2", "PandemiXium Crystal Gazer", "PandemiXium Masterpiece", "PandemiXium Weather Report", "Pandemonium X Presents Wave Ravers", "Pandemonium X Presents Nightfall", "GG Nebulous", "GG Quarantine", "GG Basics", "Bad Stepmaniacs", "Bad Stepmaniacs 2", "Maxx Simz #1", "Valex Sims 2023", "Highflyer's Tech Trails - Korean Air (with BGA videos)", "Highflyer's Tech Trails - Korean Air (videoless)", "The Longest Day", "global namespace 3 ~kernel mode~", "zib's sons", "Bass Tester Extreme", "Zaia's Dance Dance Rebuild + Expansion 1", "Lumi's Lighthouse 2", "Highflyer's Memories of Summer", "Bite-Sized Bangers", "TECH Spectrum", "val's grinds 1", "TakTek 2", "Eventual Ascension 2", "Tech-Bit Adventures 2", "zib's hip Hop", "who asked", "Getting Higgy With It", "dimocracy 3: raucous caucus", "Barber Cuts 3", "Egg Carton", "Kerpa's Simfiles Collab Pack #2", "Technical Deficiency Exam 2", "Horniest Pack in the World", "BPM (Bangerz Per Minute)", "Shpadoinkle's Techsterity #2", "Watch Out Kigha", "Zingers Exclusively", "Tech Heavy Charts (THC)", "Siriusmo Stepped", "Sky's Birthmas", "Secret Stepfile Santa 2023", "Steps of Kivotos Vol. 1: Abydos Shuffle", "sodium chloride vol. 1", "Legendz", "Kou!", "Valex Sims 2022", "7guys1pack", "Shpadoinkle #10", "Highflyer's Tech-nically Romantic", "Bass Tester Extreme", "sorae's stax", "WRSW'S WHIRLWIND", "skittles prime", "Highflyer's Tech Trails 2", "Bangers Only 3", "Hellkite's Tech-ology 1", "dimocracy 2021: second term", "Summer Vibes Vol. 1", "Lovely Techs 4", "Lovely Techs 4 (null offset)", "Kingly's Excellent Mix 4", "Fanatik's Fantastic Pack: Ascension!", "Kawaii-nesis 2", "Tak's Meta Steps (ITG Version)", "Kerpa's Simfiles Playlist 3", "Highflyer's Technically Terrifying (no BG videos)", "Highflyer's Technically Terrifying (yes BG videos)", "ULTRA PARTY MIXTAPES", "C's Meticulously Masochistic Files", "Braeden's Technicality", "Polyphia", "Koreyja 3.5", "Kangaroo Crossover", "Secret Stepfile Santa 2022", "Animal Crossover", "global namespace 2", "Prickly Pear's Poppin' Pack (Full)", "Technical Double Showcase", "Kingly's Excellent Mix 2", "Kerpa's Simfile Playlist 2", "LovelyTechs 3.1", "Resonant Earth", "Rakkii's Extra Cool Tech ANGLES", "TakTek", "Bangers Only 2", "Highflyer's Tech Trails", "Takao's Cherry Blossoms", "Kingly's Excellent Mix 3", "Star Tech", "Super Skittles Selection Turbo", "Secret Stepfile Santa 2021", "Kerpa's Simfiles Collab Pack", "Valex Sims 2021", "dimo's -VI- selifmis", "Rikame's Simfiles 7", "BemaniBeats 6", "Loodee Simfiles 2", "DVogan's Tech Support 3", "Shane's Steps", "Merge", "StoryTime Chapter 1.5", "Kerpa's Simfile Playlist", "global namespace", "Lovely Techs 2", "Skittles Selection 8", "Postmodern Technology", "FrankenFILE", "Mojo's Bizarre Tablature", "Valex Sims 2020", "Shpadoinkle #9", "Bangers Only", "Sudziosis 5.5", "dimo's -V- selifmis", "dimocracy", "jelly down the stream", "Rikame's Simfiles 6", "N.E.O. SiMS 2", "Loak's Inferno", "Silverlution", "5Guys1Pack", "Lovely Techs", "Skittles Selection 7", "Oops! All Tricks!", "CND9's Belligerent Charts", "Notice Me Benpai 2", "Kigha's Best of Both Worlds", "ITGAlex's Compilation 4", "Kacpi is _underjoyed", "Not Even Remotely Poppy", "Barely Playable", "Fraxtil's Monstercat Minipack", "DVogan's Tech Support 2", "SwageSteps 2", "Feraligatr Scales 3", "Chicago Timing Authority", "TYLR's Technical Difficulties", "BemaniBeats 5", "FA and Chill 2", "DVogan's Tech Support", "Lots of Snazzy Simfiles", "BemaniBeats Rev", "Notice Me Benpai", "N.E.O SiMS", "3guys1pack", "ITL"} \
 for packname in ivalues(streamPacks) do \
  if string.find(self:GetText(), packname, 1, true) then self:DiffuseAndStroke(color("#FF2626"), color("#000000")) self:visible(false) else self:visible(false) end \
 end \
 for packname in ivalues(technicalPacks) do \
  if string.find(self:GetText(), packname, 1, true) then self:diffuse(color("#54b9ff")) self:visible(false) else self:visible(false) end \
 end \
end
```

- Makes song folder names have a drop shadow, and removes the text when a folder is open to use with zmod option show folder banner. (The above code covers that) 

## Usage
If you would like to add a pack to a color type, you need to add it to the list inside of the metrics.ini inside SectionCollapsedSetCommand & SectionExpandedSetCommand. there are only two defined color types. Then replace your current metrics.ini with this one, or copy the code blocks into the metrics.ini in your Simply Love Theme folder, load the game, and voila!
 - Tech: Light Blue colored
 - Stamina: Red colored.

Stamina Packs
```lua
local streamPacks = {"Cathardio", "Arc Stream Works - Mission Mode", "Kyypakkaus 3", "SX14", "SX18", "MWOK's Stream Pack", "Big Bag 3", "Psytrance Division 1", "Arc Stream Works", "Sunday Night Streamin'", "Squirrel Metal II", "Posty", "Posty (Mirror)", "I wish it were always midnight", "Xynn's Inferno", "Sefirot'S SimfileS 5", "pack of charts", "EDW Sound Team \"Σ\"", "BangerZ 3", "Psytrance Division 2", "Classical Classics", "StarryPop Pt. 1", "Shit", "The Starter Pack of Stamina 2", "Big Wong", "69 Bayard", "Chase'ing' The Pack 3", "Delins Incredibly Cool Content", "VGMixtape", "BIGSTAMINA SHARPNEL", "Theoretical touhou", "Jubeat fof", "Linkin Pack", "tyler.ini", "Hospitality Hotfix", "Stamina Secret Santa 2023", "Kyypakkaus 2.5", "SiIvaStreams", "Kyypakkaus 2", "The Joy of Streaming 2", "Stam Snack Pack", "Unbuild of Sharpnel", "HISA Sim v5", "MetaJawnz", "vocaloid is hard 2", "fof no Kirby 64", "Dingoshi Ramen 2", "Dingoshi Ramen 3 Arch", "Chase'ing' The Pack 2.5", "SPAM TOONS 2", "Feelin' Rusty 4", "Xynn's Mix Tapes", "donk is hard", "Hard 2", "nebi time", "The Kellection 2", "tyler.exe", "Manwich's Stream to Midnight", "vocaloid is fast", "PUYO STREAMS 2", "Stamina Secret Santa 2022", "weeb.exe", "Joy of Streaming", "chimichungus", "vocaloid is hard", "Eurobeat Is Fantastic - Second Stage", "Enjou Stamina Package", "Gym Intervals", "the", "Short Snack Simfiles", "Lindsey Stirling", "Mango's Microrave Samplur", "Enjej Stamina Pack", "Simfile Torah", "Braeden's DDR Dumps", "DDRStream Post Supernova", "selected yutsi works", "Stam Cell Research", "touhou is hard", "barbecue lin's $5 pack of stamtech shit", "Stamina Showcase 3 Qualifiers", "Dampstream Full", "big bag", "Hard", "ExJam09 Jams 2", "epic", "yutsi B-sides", "Stamina Alley Part 1 (of 6)", "Zaniel's Junts 2", "selected yutsi works vol. 2", "MONEY MiNiPACK", "Saitama's Ultimate Weapon", "Saitama's Starter Weapon", "Tachyon Lite", "Hardbass Madness 2", "CHASE'ING' THE PACK 2", "MASNA BIEŻNIA", "Stamina Showcase 3", "fofmas 2 but its actually the finished version and not the 16 different half done folders i have on my computer for some reason", "Sick Music for stamina", "Bigger Waves", "Stamina Secret Santa 2021", "Sefirot'S SimfileS 3", "Africa Coast Stamina 1.0", "BeaTrance", "HISA Sim v3", "ExJam09 Jams", "Jayrocking", "Gloryhammer", "fsorae's fstamina ffuckeronis", "DJ Myosuke", "The Starter Pack of Stamina", "Gram Requiem", "BaguetteStreamz 2.5", "Hiiro's Metal Streamz", "Zaniel's Junts", "Jimmy Jawns 4", "Takamachi Walk - wither", "Enjoy Stamina Pack", "Slav Streamz", "Slipstreams", "Skittles Stream Collection", "HISA Sim v4", "Jynx Does Streaming", "yutsi's bass dumpz", "brakecore", "Bass Chasers", "Noah", "PANIKOx II", "138 Is Great", "Kyypakkaus", "Dark Psychungus", "Pendulum Act III", "RGM Extended", "Rhapsody Suites", "ITGAlex's Stamina Singles ep.1", "Goreshit 2020", "itg! Rhythm is just a step away", "fof 2", "Stamina Secret Santa 2020", "yutsi-type beats", "kelly's sm0l stamina pack", "ITGAlex's Stamina Safari", "StoryTime Chapter 1", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "Xynn's LVTS 2", "Euphoreyja", "Demetori ACT I", "Hardbass Madness", "a_hisa stamina v0", "Ch!pzanity", "Petriform's Factory", "StreamVoltex ep.2", "HISA Sim v2", "SlowStreamz", "Resistance Device", "The Kellection", "Dingoshi Ramen", "Stamina Secret Santa 2019", "TranceMania", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "Scrapyard Kent", "Loak STREaMS II", "Lama Freeform Pack 2018", "Death Grips", "Hospitality", "ElEson and Carmelo Minipack", "In The Dump", "Trails of Cold Stream III", "BangerZ 2", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Stamina Showcase 2", "Dampstream 2", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Getty", "Parole Violation", "DimersDozen", "Cuties Party", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Eurobeat Is Fantastic", "FusionStreamz", "can't spell 'christmas' without 'stam'", "Stamina RPG", "Chipzanity", "ECS", "Girls Coast Stamina", "Helblinde", "Pendulum", "Freyja's Grimoire"}
```
Technical Packs
```lua
local technicalPacks = {"Mute Sims X2", "Fred Figglehorn Christmas Minipack", "beat & flow", "Highflyer's Tech Trails 3", "global namespace ~callback~", "zib's hip Hop", "New Years' Stepfile Feast 2023/24", "scryptstagram", "C's Mildly Malevolent Files", "kindly produce a sound", "Rakkii's Raving Records", "9guys1pack", "Hardstyle Goes Hard", "Lovely Techs 5", "Fanatik's Fantastic Pack: Bravery", "XMOD Spectrum", "Hunter's Pack", "Highflyer's Tech-nically Romantic 2", "Shpadoinkle's TECHSTERITY", "Fanatik's Fantastic Pack of LOOOOVE", "Simply Momo & Friends Episode 1", "Kingly's Excellent Mix 5", "Lemonade (updated April 01 2023)", "Technical Proficiency Exam 2", "Valex Sims 2023", "val's minigrinds: vicious", "val's minigrinds (gec heavy charts)", "Eventual Ascension", "ITG Level Asian", "ITG Level Asian Your Smile lowers patch", "gielinor sounds", "Maractus Package", "Shut Up and Take My Money, Benpai", "Summer Vibes Vol. 2", "7gays1pack", "7gays1pack mods patch", "Tech-Bit Adventures", "DieAtic", "Orcacore", "Neo Wax Bloom", "Star Tech The Next Generation", "global namespace 3", "Zaia's Dance Dance Rebuild", "Tev's New Pack of Simfiles 1", "DRILLBOT HITECH", "Braeden's Technicality 2", "PandemiXium Crystal Gazer", "PandemiXium Masterpiece", "PandemiXium Weather Report", "Pandemonium X Presents Wave Ravers", "Pandemonium X Presents Nightfall", "GG Nebulous", "GG Quarantine", "GG Basics", "Bad Stepmaniacs", "Bad Stepmaniacs 2", "Maxx Simz #1", "Valex Sims 2023", "Highflyer's Tech Trails - Korean Air (with BGA videos)", "Highflyer's Tech Trails - Korean Air (videoless)", "The Longest Day", "global namespace 3 ~kernel mode~", "zib's sons", "Bass Tester Extreme", "Zaia's Dance Dance Rebuild + Expansion 1", "Lumi's Lighthouse 2", "Highflyer's Memories of Summer", "Bite-Sized Bangers", "TECH Spectrum", "val's grinds 1", "TakTek 2", "Eventual Ascension 2", "Tech-Bit Adventures 2", "zib's hip Hop", "who asked", "Getting Higgy With It", "dimocracy 3: raucous caucus", "Barber Cuts 3", "Egg Carton", "Kerpa's Simfiles Collab Pack #2", "Technical Deficiency Exam 2", "Horniest Pack in the World", "BPM (Bangerz Per Minute)", "Shpadoinkle's Techsterity #2", "Watch Out Kigha", "Zingers Exclusively", "Tech Heavy Charts (THC)", "Siriusmo Stepped", "Sky's Birthmas", "Secret Stepfile Santa 2023", "Steps of Kivotos Vol. 1: Abydos Shuffle", "sodium chloride vol. 1", "Legendz", "Kou!", "Valex Sims 2022", "7guys1pack", "Shpadoinkle #10", "Highflyer's Tech-nically Romantic", "Bass Tester Extreme", "sorae's stax", "WRSW'S WHIRLWIND", "skittles prime", "Highflyer's Tech Trails 2", "Bangers Only 3", "Hellkite's Tech-ology 1", "dimocracy 2021: second term", "Summer Vibes Vol. 1", "Lovely Techs 4", "Lovely Techs 4 (null offset)", "Kingly's Excellent Mix 4", "Fanatik's Fantastic Pack: Ascension!", "Kawaii-nesis 2", "Tak's Meta Steps (ITG Version)", "Kerpa's Simfiles Playlist 3", "Highflyer's Technically Terrifying (no BG videos)", "Highflyer's Technically Terrifying (yes BG videos)", "ULTRA PARTY MIXTAPES", "C's Meticulously Masochistic Files", "Braeden's Technicality", "Polyphia", "Koreyja 3.5", "Kangaroo Crossover", "Secret Stepfile Santa 2022", "Animal Crossover", "global namespace 2", "Prickly Pear's Poppin' Pack (Full)", "Technical Double Showcase", "Kingly's Excellent Mix 2", "Kerpa's Simfile Playlist 2", "LovelyTechs 3.1", "Resonant Earth", "Rakkii's Extra Cool Tech ANGLES", "TakTek", "Bangers Only 2", "Highflyer's Tech Trails", "Takao's Cherry Blossoms", "Kingly's Excellent Mix 3", "Star Tech", "Super Skittles Selection Turbo", "Secret Stepfile Santa 2021", "Kerpa's Simfiles Collab Pack", "Valex Sims 2021", "dimo's -VI- selifmis", "Rikame's Simfiles 7", "BemaniBeats 6", "Loodee Simfiles 2", "DVogan's Tech Support 3", "Shane's Steps", "Merge", "StoryTime Chapter 1.5", "Kerpa's Simfile Playlist", "global namespace", "Lovely Techs 2", "Skittles Selection 8", "Postmodern Technology", "FrankenFILE", "Mojo's Bizarre Tablature", "Valex Sims 2020", "Shpadoinkle #9", "Bangers Only", "Sudziosis 5.5", "dimo's -V- selifmis", "dimocracy", "jelly down the stream", "Rikame's Simfiles 6", "N.E.O. SiMS 2", "Loak's Inferno", "Silverlution", "5Guys1Pack", "Lovely Techs", "Skittles Selection 7", "Oops! All Tricks!", "CND9's Belligerent Charts", "Notice Me Benpai 2", "Kigha's Best of Both Worlds", "ITGAlex's Compilation 4", "Kacpi is _underjoyed", "Not Even Remotely Poppy", "Barely Playable", "Fraxtil's Monstercat Minipack", "DVogan's Tech Support 2", "SwageSteps 2", "Feraligatr Scales 3", "Chicago Timing Authority", "TYLR's Technical Difficulties", "BemaniBeats 5", "FA and Chill 2", "DVogan's Tech Support", "Lots of Snazzy Simfiles", "BemaniBeats Rev", "Notice Me Benpai", "N.E.O SiMS", "3guys1pack", "ITL"}
```

The lists above should contain all packs labelled as Technical or Stream from Current(March 20th, 2024) - 2017. Due to the sheer amount of packs, don't expect that EVERY pack should be there, there are hundreds and hundreds of packs probably not in this list, but the most modern and latest ones should be! Always use these two list codeblocks to get the most updated pack lists as the one in metrics.ini may not be up to date.

## Credits
Zmod Simply Love: https://github.com/zarzob/Simply-Love-SM5
