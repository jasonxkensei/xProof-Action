# notarize-action

## Release v1.0.0

This release marks the initial version of the `notarize-action` GitHub Action.

### Features
- Automates the notarization process of applications on macOS.
- Supports multiple file formats including .app, .pkg, and .dmg.
- Provides logging and error handling to ensure successful notarization.

### Setup
1. **Create a Personal Access Token**: You need a personal access token with access to your Apple Developer account.
2. **Add Secrets to Your Repository**: Add your Apple ID and App Specific Password as secrets in your repository settings.
3. **Use the Action in Your Workflow**:
   ```yaml
   name: Notarize App
   on: [push]
   jobs:
     notarize:
       runs-on: macOS-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v2
         - name: Notarize
           uses: jasonxkensei/notarize-action@v1.0.0
           with:
             apple-id: ${{ secrets.APPLE_ID }}
             app-specific-password: ${{ secrets.APP_SPECIFIC_PASSWORD }}
             file: path/to/file.pkg
   ```

Enjoy using the notarize-action!