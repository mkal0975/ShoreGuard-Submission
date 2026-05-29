# ShoreGuard

A Microsoft Power Apps application for shore and coastal management operations.

## Overview

ShoreGuard is a canvas-based Power Apps solution designed to support field operations, reporting, and resource management for coastal environments. The app is built with a modular structure separating UI controls, data resources, and business logic.

## Repository Structure

```
ShoreGuard/
├── AppTests/                          # App testing and test cases
├── Assets/Images/                     # Image assets used throughout the app
├── Controls/                          # Reusable UI control definitions
├── References/                        # External references and dependencies
├── Resources/                         # App resources (fonts, icons, etc.)
├── Src/                               # Source screens and component logic
├── AppCheckerResult.sarif             # Power Apps static analysis / App Checker results
├── Header.json                        # App header metadata
├── Properties.json                    # App-level properties and configuration
├── ShoreGuard - Technical Documentation.pdf  # Technical architecture and developer docs
├── ShoreGuard - User Guide.pdf        # End-user documentation
└── ShoreGuard.msapp                   # Compiled Power Apps package file
```

## Getting Started

### Prerequisites

- Microsoft Power Apps (licensed environment)
- Access to the relevant SharePoint / Dataverse data sources (see Technical Documentation)

### Importing the App

1. Sign in to [make.powerapps.com](https://make.powerapps.com)
2. Navigate to **Apps** → **Import canvas app**
3. Upload `ShoreGuard.msapp`
4. Follow the import wizard to map connections and data sources
5. Save and publish the app

### Running from Source

The `/Src` directory contains the unpacked app source, which can be used with the [Power Platform CLI](https://learn.microsoft.com/en-us/power-platform/developer/cli/introduction) for version-controlled development:

```bash
# Pack source into .msapp
pac canvas pack --sources ./Src --msapp ShoreGuard.msapp

# Unpack .msapp back to source
pac canvas unpack --msapp ShoreGuard.msapp --sources ./Src
```

## Documentation

1. **[User Guide](./ShoreGuard%20-%20User%20Guide.pdf)** — Instructions for end users on navigating and using the app
2. **[Technical Documentation](./ShoreGuard%20-%20Technical%20Documentation.pdf)** — Architecture, data sources, configuration, and developer reference
3. **[Reflection](./ShoreGuard%20-%20Reflection.pdf)** — Project reflections, lessons learned, and retrospective notes
4. **[Q&A + Testing](./ShoreGuard%20-%20Q%26A%20%2B%20Testing.pdf)** — Questions, answers, and testing outcomes

## Code Quality

Static analysis results are stored in `AppCheckerResult.sarif` and can be viewed in any SARIF-compatible viewer (e.g. the SARIF Viewer extension for VS Code) or reviewed directly in Power Apps Studio via the App Checker panel.

## Testing

Test cases are located in the `/AppTests` directory and can be run via the Power Apps Test Studio within your environment.

## Contributing

1. Unpack the `.msapp` using the Power Platform CLI (see above)
2. Make changes in the `/Src` directory
3. Repack and test before committing
4. Ensure App Checker passes with no critical issues before raising a pull request
