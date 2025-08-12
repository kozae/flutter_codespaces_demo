# flutter_simple_todo

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## GitHub Pages Deployment

This project is configured to automatically deploy the Flutter web app to GitHub Pages using GitHub Actions.

### Automatic Deployment

The app will automatically deploy to GitHub Pages when you push to the `main` branch. You can also trigger a manual deployment by going to the **Actions** tab and running the "Deploy Flutter Web to GitHub Pages" workflow.

### Manual Configuration Required

To enable GitHub Pages deployment, you need to configure the following settings in your GitHub repository:

1. **Enable GitHub Pages:**
   - Go to your repository **Settings** tab
   - Scroll down to the **Pages** section in the left sidebar
   - Under **Source**, select "**GitHub Actions**" (not the legacy "Deploy from a branch" option)
   - Save the settings

2. **Repository Visibility:**
   - GitHub Pages is available for public repositories on free accounts
   - For private repositories, you need a GitHub Pro, Team, or Enterprise account

3. **Access Your Deployed App:**
   - After successful deployment, your app will be available at:
   - `https://[your-username].github.io/flutter_simple_todo/`
   - The URL will be displayed in the Actions workflow output

### Troubleshooting

- **404 Error:** Make sure you've enabled GitHub Pages with "GitHub Actions" as the source
- **Deployment Failed:** Check the Actions tab for error details in the workflow logs
- **Base URL Issues:** The app is configured to work at `/flutter_simple_todo/` - if you rename the repository, update the base-href in the workflow file
- **Permissions Error:** Ensure the repository has the required permissions for Pages deployment

### Customizing the Deployment

The deployment configuration is in `.github/workflows/deploy-pages.yml`. Key settings:

- **Base URL:** Currently set to `/${{ github.event.repository.name }}/` (auto-detects repo name)
- **Trigger:** Runs on push to `main` branch and manual dispatch
- **Build:** Uses Flutter stable channel with release optimization

If you rename the repository, the base URL will automatically update. For custom domain deployment, modify the base-href parameter in the workflow file.
