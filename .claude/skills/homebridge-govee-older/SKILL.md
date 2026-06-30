```markdown
# homebridge-govee-older Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the development patterns and workflows for the `homebridge-govee-older` JavaScript codebase. The repository focuses on integrating Govee devices with Homebridge, allowing users to add or enhance device support. It follows consistent coding conventions and a clear workflow for extending device compatibility.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `deviceHandler.js`, `lightUtils.js`

### Import Style
- Use **relative imports** for modules within the project.
  - Example:
    ```js
    const constants = require('../utils/constants');
    ```

### Export Style
- Use **default exports** for modules.
  - Example:
    ```js
    module.exports = DeviceHandler;
    ```

### Commit Messages
- Use **Conventional Commits** with the `feat` prefix for new features.
  - Example:
    ```
    feat: add support for H6002 light model
    ```

## Workflows

### Add or Enhance Device Support
**Trigger:** When you want to add support for a new device model or improve support for an existing device (e.g., new light, new zone handling).  
**Command:** `/add-device-support`

1. **Update device handling logic:**
   - Add the new model to the appropriate constants file:
     ```js
     // lib/utils/constants.js
     const SUPPORTED_MODELS = [
       'H6001',
       'H6002', // newly added
       // ...
     ];
     ```
   - Enhance or add the device handler logic:
     ```js
     // lib/device/light.js
     if (model === 'H6002') {
       // Handle new device specifics
     }
     ```
2. **Update the changelog:**
   - Document the new or improved device support in `CHANGELOG.md`:
     ```
     - Added support for Govee H6002 light model
     ```

## Testing Patterns

- **Framework:** Unknown (no framework detected).
- **File Pattern:** Test files use the `*.test.*` naming convention.
  - Example: `deviceHandler.test.js`
- **Typical Test Example:**
  ```js
  // deviceHandler.test.js
  const DeviceHandler = require('./deviceHandler');

  test('should handle H6002 model', () => {
    // test logic here
  });
  ```

## Commands

| Command             | Purpose                                             |
|---------------------|-----------------------------------------------------|
| /add-device-support | Add or enhance support for a specific device model. |
```
