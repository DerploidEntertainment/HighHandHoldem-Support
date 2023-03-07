# Changelog

All notable changes to _High Hand Hold'em™_ are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## 0.5.0 - 2023-02-13

### Added in 0.5.0

- Set "ITSAppUsesNonExemptEncryption" to false for iOS builds. All of this game's encryption is exempt from US export compliance law
- Added "NSUserTrackingUsageDescription" permission for iOS builds, to allow advertising identifier usage in iOS 14.5+
- Support for x86 x86-64 ChromeOS devices (untested though)
- Sounds for when cards flip and slide on the gameboard
- Button on Statistics screen for resetting stats
- New website for Derploid and _High Hand Hold'em_ at www.derploid.com! Hosted on GitHub Pages, with domains registered and DNS configured through AWS Route53.
- Sign-up form for Derploid mailing list to the new website, powered by Sendinblue.
- Consent opt-out buttons for ads and analytics, to make the game compliant with GDPR and other privacy regulations
- Warning about lost progress to confirm-quit text in Pause menu
- Internal: AWS resources behind the new website are encoded using the Cloud Development Kit (CDK), rather than CloudFormation Templates directly.
- Internal: .NET Analyzers for better static analysis of code
- Internal: script to generate thousands of deals with random inputs to test out the new procedural dealing logic
- Internal: scripts to generate local Android/iOS builds for troubleshooting failed Unity Cloud Builds
- Internal: Ultimate Editor Enhancer asset to improve Unity workflow

### Changed in 0.5.0

- Procedural dealing logic to generate deals of all ranks with equal probability, while maintaining variability.
  - Deals are generated in the background to keep a consistent frame rate between rounds
  - A permutation of all Poker ranks is batched ahead of time for choosing the winning rank, with 0-3 "runs" per batch, each 2-3 repeats long.
    This ensures all ranks win with approximately equal probability, while preventing the same rank from winning too many rounds in a row,
    or from not appearing for too many rounds in a row, as might happen if we dealt truly randomly.
- Texture compression settings on all images for Android, achieving ~10% smaller APK download size and ~24% less memory consumption at runtime
- Texture compression settings on all images for iOS, achieving ~80% smaller IPA download size and install size, and ~94% less memory consumption at runtime
- Continue button after a wrong choice to have "OK" text, rather than a thumbs-up icon
- Minimum target iOS version down to 12.2
- Minimum target Android API Level up to 22 (Android 5.1 "Lollipop")
- Combined two FTUE (first-time user experience) dialogs into one, with updated wording
- Poker rank stats to report as % accuracy, not number of correct guesses
- Poker rank correct effects to always "pop" the cards in increasing order
- Support repo issue templates now use GitHub Issue Forms for better formatting and input validation
- Analytics system from Unity's Legacy Analytics to Unity Game Service analytics, for better performance and compliance with privacy laws
- Board cards and hands to be hidden until they are in play, with an animation as they are added
- Credits on About screen to more accurately reflect our team roles
- "Powered By" section of About screen to more accurately reflect our tech dependencies
- Internal: updated Unity version to 2021.3 LTS (with Gradle 6.1.1)
- Internal: all code now targets .NET Standard 2.1 after Unity update
- Internal: Android Gradle Plugin version to 4.0.1
- Internal: Appodeal SDK version to 2.15.4
- Internal: our iOS builds are now automatically submitted to App Store Connect from Unity Cloud Build, streamlining our CI/CD pipeline
- Internal: updated Nice Vibrations asset to the new Lofelt version (v4.1.0)
- Internal: local Android builds to use a separate app ID so local test builds, debug cloud builds, and prod cloud builds can coexist on the same device.
- Internal: all internal repo "master" branches to "main", to use more inclusive language
- Internal: added the OpenUPM and UnityNuGet UPM package registries, allowing us to use NuGet packages in this project and simplify local build configurations
- Internal: logging is now handled by Serilog
- Internal: disabled bitcode on iOS, as recommended for Xcode 14+
- Internal: assembly version of custom assemblies are now always in sync with Unity project version

### Removed in 0.5.0

- "Contact Support" button from About screen (making a bug report or feature request on GitHub is recommended instead)
- iOS launch screen image

### Fixed in 0.5.0

- "Loading" text on splash screen to use same font as other UI
- Low-pass filter not applying to music on the pause menu
- Value formatting on Statistics screen to always include leading zeroes for decimals, and use integer values for scores and numbers of rounds

## 0.4.0 - 2021-02-18

### Added in 0.4.0

- A basic, placeholder tutorial for introducing the Poker ranks and rules specific to High Hand Hold'em. The tutorial will not show again after its been completed, unless player toggles it back on for the next game from the Options menu
- Appodeal 2.11.2 for ad mediation
- Runtime configuration via Unity Remote Config
- A sound for when UI elements are tapped
- New "announcer callouts" for starting a game
- New "announcer callouts" for continuing a game
- New "announcer callouts" for timeout and gameover
- New "announcer callout" for longest game
- iOS launch screen image

### Changed in 0.4.0

- Now running with Unity 2020.1.8f1
- Banner ad now shows on Pause menu
- Font size on "rectangle buttons" is larger
- Image for the button to continue after a wrong choice or timeout
- Minimum target iOS version to 12.4, and minimum Android version to 5.0 "Lollipop", to simplify maintenance of all the new Android/iOS plugins added by Appodeal
- The overall art style has been updated.
- Border light animation to a single pulse of all lights
- Unselected cards no longer "un-dim" before flipping over after a correct choice
- Scene loading time is now ~37% faster on iOS (unchanged on Android), with ~35% less heap memory allocated on Android and ~63% less on iOS!
- First time loading the game screen in a session is now ~25% faster on Android and ~21% faster on iOS, with ~64% less heap memory allocated on Android and ~60% less on iOS!
- Changed "announcer callouts" for hand ranks.
- Changed "announcer callout" for new high score.
- Game will now fit to the "safe area" of the screen on notched devices like iPhone 11

### Removed in 0.4.0

- Unnecessary analytics events for visiting the Main Menu
- "Today" and "This Week" stats, as they didn't really add much value for a single player's stats

### Fixed in 0.4.0

- Checkboxes on the Options screen not being tappable after navigating from the Pause menu
- Procedural dealing is now better documented and configurable for our level designers
- Back button logging errors from Main Menu or during a game
- Banner ad staying visible when navigating from side menus to Main Menu or from Pause menu back to game

## 0.3.0 - 2020-07-23

### Added in 0.3.0

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

### Changed in 0.3.0

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

### Removed in 0.3.0

- Commit SHA from About screen, since it was meaningless to players, and devs can figure out from CI/CD system
- That bouncy shadow under the circle light behind the "Hold'em" letters
- That sketchy, "pencily" shader effect from the cards

### Fixed in 0.3.0

- Hands still being clickable on timeout
- Cards not being dealt with tiered difficulty (with respect to number of board/hand cards)
- UI controls on scrollable screens being hard to press
- Sharp corners in the board area and game area
- Broken tiling of the patterned background, and made it fit the color scheme better

## 0.2.0 - 2020-01-15

### Added in 0.2.0

- Instertitial ads after every 3rd gameover, because monetization
- Volume of music, SFX, and announcer audio can now be adjusted with sliders in Options menu
- Audio values set in Options menu will be persisted between sessions
- Default 512x512 app icon

### Changed in 0.2.0

- Now running with Unity 2019.2.17f1
- High score screen can now show up to 10 scrollable tiles

## 0.1.0 - 2019-12-22

### Added in 0.1.0

- First version of the game built with a semantic version
