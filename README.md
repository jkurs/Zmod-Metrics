# Zmod-Metrics
Backup of my edits to Zmod Simply Love Theme for ITG Mania

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
 local streamPacks = {"SX14", "SX18", "MWOK's Stream Pack", "Big Bag 3", "Arc Stream Works", "Sunday Night Streamin'", "Squirrel Metal 2", "Posty", "I wish it were always midnight", "Xynn's Inferno", "Sefirot'S SimfileS 5", "pack of charts", "EDW Sound Team \"Σ\"", "BangerZ 3", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "StreamVoltex ep.2", "In The Dump", "Trails of Cold Stream III", "Scrapyard Kent", "Tachyon Zeta", "Lama Freeform Pack 2018", "SlowStreamz", "Resistance Device", "The Kellection", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "Content Cop - Tachyon Epsilon", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Barber Cuts", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "Eurobeat Is Fantastic", "Cuties Party", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Getty", "Parole Violation", "FusionStreamz", "can't spell 'christmas' without 'stam'", "The Starter Pack of Stamina", "Stamina Secret Santa 2019", "Stamina Secret Santa 2023", "The Longest Day", "Shut Up and Take My Money, Benpai", "Hospitality", "Stamina Showcase 2", "Stamina Showcase 3", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Feelin' Rusty 4", "Trails of Cold Stream", "The Starter Pack of Stamina 2", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "Loak STREaMS II", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "StreamVoltex ep.2", "In The Dump", "Trails of Cold Stream III", "Scrapyard Kent", "SlowStreamz", "Resistance Device", "Getty", "Parole Violation", "Content Cop - Tachyon Epsilon", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "BaguetteStreamz", "Trails of Cold Stream", "Eurobeat is Fantastic", "Cuties Party", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Trails of Cold Stream II", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "FusionStreamz", "Stamina RPG", "ECS", "Chipzanity", "Dingoshi Ramen 3 Arch", "ExJam09 Jams 2", "Freyja's Grimoire", "Girls Coast", "Hardbass Madness", "Helblinde", "itg! Rhythm is just a step away!", "ITGAlex's Stamina Safari", "Jayrocking", "Lindsey Stirling", "Pendulum", "Saitama's Starter Weapon", "Short Snack Simfiles", "Slipstreams", "Squirrel Metal II", "The Joy of Streaming", "TranceMania", "Unbuild of Sharpnel", "Xynn's Mix Tapes", "Tuuc's Stam Snack Pack"} \
local technicalPacks = {"Mute Sims X2", "Fred Figglehorn Christmas Minipack", "beat & flow", "Inner Depths", "Highflyer's Tech Trails 3", "global namespace ~callback~", "zib's hip Hop", "New Years' Stepfile Feast 2023/24", "scryptstagram", "C's Mildly Malevolent Files", "Dragonforce 2013", "Hunter's Bounties", "kindly produce a sound", "Rakkii's Raving Records", "9guys1pack", "Hardstyle Goes Hard", "Lovely Techs 5", "Bumble's Steps", "7guys1pack", "Animal Crossover", "Bangers Only", "BemaniBeats", "dimocracy", "ITGAlex's Compilation 4", "Notice Me Benpai", "Prickly Pear's Poppin' Pack", "sorae's stax", "Summer Vibes Vol. 1", "ITL"} \
 for packname in ivalues(streamPacks) do \
  if string.find(self:GetText(), packname, 1, true) then self:diffuse(color("#FF2626")) self:shadowlengthx(0) self:shadowlengthy(1) self:shadowcolor(0,0,0,1) end \
 end \
 for packname in ivalues(technicalPacks) do \
  if string.find(self:GetText(), packname, 1, true) then self:diffuse(color("#54b9ff")) self:shadowlengthx(0) self:shadowlengthy(1) self:shadowcolor(0,0,0,1) end \
 end \
end
SectionExpandedSetCommand=%function(self) DiffuseEmojis(self) self:diffuse(1,1,1,1) \
 local streamPacks = {"SX14", "SX18", "MWOK's Stream Pack", "Big Bag 3", "Arc Stream Works", "Sunday Night Streamin'", "Squirrel Metal 2", "Posty", "I wish it were always midnight", "Xynn's Inferno", "Sefirot'S SimfileS 5", "pack of charts", "EDW Sound Team \"Σ\"", "BangerZ 3", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "StreamVoltex ep.2", "In The Dump", "Trails of Cold Stream III", "Scrapyard Kent", "Tachyon Zeta", "Lama Freeform Pack 2018", "SlowStreamz", "Resistance Device", "The Kellection", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "Content Cop - Tachyon Epsilon", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Barber Cuts", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "Eurobeat Is Fantastic", "Cuties Party", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Getty", "Parole Violation", "FusionStreamz", "can't spell 'christmas' without 'stam'", "The Starter Pack of Stamina", "Stamina Secret Santa 2019", "Stamina Secret Santa 2023", "The Longest Day", "Shut Up and Take My Money, Benpai", "Hospitality", "Stamina Showcase 2", "Stamina Showcase 3", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "Feelin' Rusty 4", "Trails of Cold Stream", "The Starter Pack of Stamina 2", "Cirque du Enzo", "Rebuild of Sharpnel", "BangerZ", "Trails of Cold Stream II", "Loak STREaMS II", "StreamVoltex ep.1", "katagiri", "Helblinde PDTA", "StreamVoltex ep.2", "In The Dump", "Trails of Cold Stream III", "Scrapyard Kent", "SlowStreamz", "Resistance Device", "Getty", "Parole Violation", "Content Cop - Tachyon Epsilon", "Digital Nightmare", "Jimmy Jawns 3", "Electricity", "BaguetteStreamz", "Trails of Cold Stream", "Eurobeat is Fantastic", "Cuties Party", "Salut C'est Cool", "Pi Pie", "Betwixt & Between", "Trails of Cold Stream II", "DVogan Streamz", "SHARPNELSTREAMZ v3 Part 2", "Cirque du Miura", "Dragonforce Kaioken", "Wapperende Benen", "BaguetteStreamz 2", "Comiket 95", "French Coast Stamina 3", "French Coast Stamina 3 - Marathons", "Psychedelia", "BaguetteStreamz", "Trails of Cold Stream", "FusionStreamz", "Stamina RPG", "ECS", "Chipzanity", "Dingoshi Ramen 3 Arch", "ExJam09 Jams 2", "Freyja's Grimoire", "Girls Coast", "Hardbass Madness", "Helblinde", "itg! Rhythm is just a step away!", "ITGAlex's Stamina Safari", "Jayrocking", "Lindsey Stirling", "Pendulum", "Saitama's Starter Weapon", "Short Snack Simfiles", "Slipstreams", "Squirrel Metal II", "The Joy of Streaming", "TranceMania", "Unbuild of Sharpnel", "Xynn's Mix Tapes", "Tuuc's Stam Snack Pack"} \
local technicalPacks = {"Mute Sims X2", "Fred Figglehorn Christmas Minipack", "beat & flow", "Inner Depths", "Highflyer's Tech Trails 3", "global namespace ~callback~", "zib's hip Hop", "New Years' Stepfile Feast 2023/24", "scryptstagram", "C's Mildly Malevolent Files", "Dragonforce 2013", "Hunter's Bounties", "kindly produce a sound", "Rakkii's Raving Records", "9guys1pack", "Hardstyle Goes Hard", "Lovely Techs 5", "Bumble's Steps", "7guys1pack", "Animal Crossover", "Bangers Only", "BemaniBeats", "dimocracy", "ITGAlex's Compilation 4", "Notice Me Benpai", "Prickly Pear's Poppin' Pack", "sorae's stax", "Summer Vibes Vol. 1", "ITL"} \
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
If you would like to add a pack to a color type, you need to add it to the list inside of the metrics.ini inside SectionCollapsedSetCommand & SectionExpandedSetCommand. there are only two defined color types.
 - Tech: Light Blue colored
 - Stamina: Red colored.

## Credits
Zmod Simply Love: https://github.com/zarzob/Simply-Love-SM5
