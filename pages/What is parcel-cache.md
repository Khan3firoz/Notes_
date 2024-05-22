# What is .parcel-cache #NodeJs 
heading:: 1

Created: February 7, 2024 12:37 AM
Updated: February 7, 2024 12:40 AM

The **.parcel-cache** directory is a directory created by the Parcel bundler during the build process. Parcel uses this directory to cache intermediate build artifacts and speed up subsequent builds.
- **Created by Parcel bundler:** Stores intermediate build artifacts.
- **Improves build performance:** Caches processed files and dependencies.
- **Safe to delete (if needed):** Forces Parcel to reprocess everything.
- **Don't version control:** Specific to build environment, regenerates easily.