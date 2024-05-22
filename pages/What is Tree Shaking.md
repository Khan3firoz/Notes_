# What is Tree Shaking? #React
heading:: 1
- Created: February 7, 2024 12:49 AM
  Updated: February 7, 2024 12:49 AM
  
  **Tree shaking** is an optimization technique used in JavaScript bundlers like Webpack and Rollup to remove unused code from your application's final bundle. Think of it like shaking an apple tree to remove the unnecessary leaves while keeping the juicy fruits (your actual code).
  
  **Here's how it works:**
- Module analysis: The bundler analyzes your code, looking at how modules are imported and exported.
- Dead code identification: It identifies code within modules that is never used (dead code).
- Elimination: This dead code is then safely removed from the final bundle.
  
  **Benefits:**
- Smaller bundle size: Smaller bundles translate to faster loading times and improved performance.
- Reduced bandwidth usage: Smaller bundles mean less data needs to be downloaded, saving internet bandwidth.
- Cleaner codebase: Less unused code makes your codebase easier to maintain and understand.
  
  **Requirements:**
- Modern JavaScript modules: Tree shaking works best with ES modules (import/export) syntax.
- Proper configuration: Your bundler might need specific configuration to enable tree shaking effectively.
  
  **Use cases:**
- Including large libraries like Lodash: Instead of including the entire library, only import the specific functions you need.
- Creating modular code: Well-organized, smaller modules enhance tree shaking benefits.