# Changelog
All notable changes to _High Hand Hold'em_ will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 0.4.0 - TBD

### Added

- A sound for when UI elements are tapped

### Changed

- Banner ad now shows on Pause menu
- Font size on "rectangle buttons" to be larger
- Stats menu shows different text when no games have been played within the different timespans

### Removed

- Unnecessary analytics events for visiting the Main Menu

### Fixed


## 0.3.0 - 2020-07-23

### Added

- This CHANGELOG file to summarize what new features and bug fixes are included in each new version
- Separate sections for Feedback & Issues, Changelog, and Legal Stuff in Support repo README
- Button on About screen that links to this Changelog (labeled "Release Notes", cause thats a more familiar term)
- Vibrations for correct/wrong choices, starting a game, timeout, etc. using More Mountains' Nice Vibrations asset
- Vibrations can be toggled on/off from Options menu (unless the device doesnt support haptics), and the choice will be persisted between sessions
- Custom icons on UI buttons
- Back button (or gesture) can be used to navigate menus on Android devices
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
- Effects for playing the new longest game, in addition to effects for new high score
- Gameover screen now shows "badges" for high score and longest game, if they were achieved during the game that just ended
- "Powered By" section on About screen that shows important technologies/assets powering the game, with links to their websites
- Now tracking multiple "stats" in addition to high score: number of games, average rounds lasted, max rounds lasted, average round time for rounds with different numbers of hands, and number of correct choices for each poker rank
- The stats number of games, high score, average rounds lasted, and max rounds lasted also have "no continue" variants, which include only stats from games where a rewarded ad was not used to continue
- All of the new stats can be filtered by "today", "this week", or "all time" on the Stats screen
- Hand Ranks screen, where players can get an overview of the different Poker ranks
- Button to open Hand Ranks screen from pause menu

### Changed
- Now running with Unity 2019.4.3f1
- Pause menu adds a low-pass filter to the background music
- Correct-choice animations feel a bit more "snappy"
- All UI now uses the Nathaniel-19 font
- Derploid logo on splash screen
- "Pop" effects on correct cards: cards for all ranks now pop in descending optimal order and do not translate
- Non-chosen cards are now dimmed, rather than making the chosen cards yellow
- Background frame, with new divider bar under board cards, only when playing
- Circular UI buttons now line up vertically for clarity
- Hold'em sign letters and light effects
- Handles of audio sliders on options screen to look like Poker chips
- Main menu shows "Main Menu" in scorebox
- Added UI "breakpoints" to update size/position of UI elements on devices with different aspect ratios
- Release builds now include additional optimizations like engine code bytecode stripping, IL2CPP Release configuration, and higher compression
- Interstitial ads will now show when quitting to main menu (from pause or gameover screens) after every 3rd gameover
- Now using incremental garbage collector
- High Score screen is now the Statistics screen, with many additional stats besides high score being tracked (see Added section above)
- UI effects for new high scores now appear/disappear, rather than staying at the top of the screen for the rest of the game
- When resuming a game after soft closing, game will be paused
- Banner ads now show on Options, Stats, About, and Hand Ranks screens as well
- Options menu has been reorganized, with audio sliders larger and their handles Poker chips instead of gems
- Version number to include build number as 4th value
- Colors to be more balanced with the Blend Modes asset
- Paused screen to show "Paused" in the scorebox
- Timer lights have a little flash animation as they tick down. When there are 5 seconds left, they flash red, and then they pulse on a loop after a timeout.
- App icon, providing round/adaptive icons for Android devices that support them
- The scroll bars on all scrollable screens
- The hand indicator lights, which are once again little bouncing chevrons
- Button backgrounds to better match the color theme
- The patterned background to a "checkerboard" rather than "zig zags"

### Removed
- Commit SHA from About screen, since it was meaningless to players, and devs can figure out from CI/CD system
- That bouncy shadow under the circle light behind the "Hold'em" letters
- That sketchy, "pencily" shader effect from the cards

### Fixed
- Hands still being clickable on timeout
- Cards not being dealt with tiered difficulty (with respect to number of board/hand cards)
- UI controls on scrollable screens being hard to press
- Sharp corners in the board area and game area
- Broken tiling of the patterned background, and made it fit the color scheme better


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
