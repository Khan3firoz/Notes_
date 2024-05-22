# What is `.gitignore`? #Git 
heading:: 1

Created: February 7, 2024 12:53 AM
Updated: February 7, 2024 12:55 AM

**A .gitignore File** is a special text file used in version control systems like Git to specify files and folders that should be excluded from being tracked and committed to the repository. This helps keep your repository clean and manageable by excluding unnecessary or sensitive files. **What to Add to .gitignore:**
- Node Module or Dependency Directories:
	- node_modules/ - Directory containing dependencies installed by npm or Yarn.
- Build Output:
	- build/ - Common directory for compiled or bundled output.
	- dist/ - Another common directory for distribution or production builds.
- Temporary Files:
	- .DS_Store - macOS system file storing custom attributes of a folder.
	- Thumbs.db - Windows system file storing thumbnails of a folder's pictures.
- IDE/Editor Files:
	- .vscode/ - Directory for Visual Studio Code settings.
	- .idea/ - Directory for JetBrains IDE settings.
- Logs and Debugging:
	- .log - Log files.
	- .debug - Debugging output.
- Configuration Files:
	- .env - Environment variable configuration files.
	- .env.local - Local overrides for environment variables.
- Dependency Management:
	- yarn-error.log - Yarn error log.
	- package-lock.json - Lock file for npm.
	- yarn.lock - Lock file for Yarn.
- Miscellaneous:
	- .gitignore - To avoid accidentally committing another .gitignore.
	- .git/ - Git directory for repository metadata.
	  
	  **What Not to Add to .gitignore:**
- Tracked Files:
	- Do not add files that are already tracked by Git. The purpose of .gitignore is to ignore untracked files.
- Sensitive Information:
	- Avoid adding sensitive information like API keys, passwords, or other secrets. Instead, use environment variables or configuration files with sensitive data excluded from version control.
- Project-Specific Files:
	- Do not add files or directories that are specific to your local development environment or tools.
- Dynamic Configurations:
	- Avoid adding configurations that change frequently, as it can make collaboration challenging. Instead, use defaults in the project and let contributors customize as needed.
- Binary Files:
	- It's generally not recommended to add binary files, such as compiled binaries, to version control. These files can bloat the repository size.