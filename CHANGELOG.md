# Changelog
All notable changes to _High Hand Hold'em_ will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

### Added

- This CHANGELOG file to summarize what new features and bug fixes are included in each new version
- Separate sections for Feedback & Issues, Changelog, and Legal Stuff in Support repo README
- Button on About screen that links to this Changelog (labeled "Release Notes", cause thats a more familiar term)
- Vibrations for correct/wrong choices, starting a game, timeout, etc. using More Mountains' Nice Vibrations asset
- Vibrations can be toggled on/off from Options menu (unless the device doesnt support haptics), and the choice will be persisted between sessions
- Custom icons on UI buttons
- Back button on Android devices can be used to navigate menus
- Buttons on About screen that link to support repo, for creating bug reports or requesting new features
- 3-2-1 countdown when starting a new game or continuing after a rewarded ad
- Hand/board cards now "fly in" when a new game starts
- "Confirm quit" buttons to the pause screen, navigable with Android back button
- A loading screen, so there's something to look at while first (and only) scene is being loaded by Unity
- Dialog for accepting legal documents on first game start or after documents are updated (privacy policy and terms/conditions not yet written)
- Acceptance of legal documents is persisted between sessions
- Shine effect to cards immediately after deal
- Button to open options screen from pause menu
- Ability to continue for free by watching a rewarded ad (only if 3 rounds since last continue or start of game)
- Now tracking longest games, in addition to high scores
- Gameover screen now shows "badges" for high score and longest game, if they were achieved during the game that just ended
- "Powered By" section on About screen that shows important technologies/assets powering the game, with links to their websites

### Changed
- Now running with Unity 2019.3.0f6
- Pause menu adds a low-pass filter to the background music
- Correct-choice animations feel a bit more "snappy"
- Cards no longer have that goofy "pencily" shader effect
- All UI now uses the KenVector Bold font
- Derploid logo on splash screen
- "Pop" effects on correct cards: cards for all ranks now pop in descending optimal order and do not translate
- Non-chosen cards are now dimmed, rather than making the chosen cards yellow
- Background frame, with new divider bar under board cards, only when playing
- Circular UI buttons now have spinning circular text around them
- Hold'em sign letters
- Handles of audio sliders on options screen are now shaped like gems
- Scorebox displays the name of the correct Poker rank
- Main menu shows "Main Menu" in scorebox
- Added UI "breakpoints" to update size/position of UI elements on devices with different aspect ratios
- The circle around the hold'em letters no longer bounces
- Release builds now include additional optimizations like engine code bytecode stripping, IL2CPP Release configuration, and higher compression
- Interstitial ads will now show when quitting to main menu (from pause or gameover screens) after every 3rd gameover
- Now using incremental garbage collector
- High Score screen is now the Stats screen, and allows stats to be sorted by score, rounds lasted, or date
- UI effects for new high scores now appear/disappear, rather than staying at the top of the screen for the rest of the game
- When resuming a game after soft closing on iOS/Android, game will be paused
- Banner ads now show on Options, Stats, and About screens as well
- Options menu has been reorganized, with audio sliders larger and their handles Poker chips instead of gems
- Build number is now 4th value of the version number

### Removed
- Commit SHA on About screen, since its meaningless to players, and devs can figure out from Cloud Build
- Scroll bars on all screens that scroll

### Fixed
- High score tiles not being wide enough
- High score tiles not displaying correct local date
- Hands still being clickable on timeout
- Cards not being dealt with tiered difficulty (number of board/hand cards)
- UI controls on scrollable screens being hard to press

## 0.2.0 - 2020-01-15

### Added
- Instertitial ads after every 3rd gameover, because monetization
- Volume of music, SFX, and announcer audio can now be adjusted with sliders in Options menu
- Audio values set in Options menu will be persisted between sessions
- Default 512x512 app icon

### Changed
- Now running with Unity 2019.2.17f1
- High score screen can now show up to 10 scrollable tiles

## 0.1.0 - 2019-12-22

### Added
- First version of the game built with a semantic version
