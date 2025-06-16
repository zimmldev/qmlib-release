# QMLib Release Repository

Welcome to the official **QMLib Release** repository! This repository hosts the pre-built binaries for QMLib, a cross-platform design system built with Qt6 to streamline and enhance UI development for QML applications.

## About QMLib
QMLib simplifies QML development by offering:
- Full implementation of Material Design 3.0 components.
- High-level, reusable UI elements to accelerate development.
- Support for multiple platforms: Linux, macOS, Windows, iOS, Android, WearOS, watchOS, and WebAssembly.

For more information about QMLib, visit:
- 🔗 [Live Demo and Gallery](https://loiczimm.com/gallery)
- 🔗 [Examples Repository](https://github.com/zimmldev/qmlib-examples)

## Getting Started

### Using QMLib Binaries
To integrate QMLib binaries into your project:
1. Download the appropriate binary release from the [Releases](https://github.com/zimmldev/qmlib-release/releases) section.
2. Follow the integration guide provided in the QMLib documentation to set up the binaries with your Qt6 environment.

## Free Usage & Licensing

QMLib is **free to use** with the following limitation:

> A notification popup will be displayed in your application footer indicating that you are using the **free version**.

To remove this notification and unlock full features, you can purchase a license.

### Purchase a License

Choose a subscription plan that suits you:

<p align="center">
  <a href="https://buy.stripe.com/bJe8wPcbH2UN2hafIA6Na01" target="_blank" style="text-decoration:none;">
    <img src="https://img.shields.io/badge/Subscribe_Yearly-blue?style=for-the-badge&logo=stripe&logoColor=white" alt="Yearly Subscription" />
  </a>
  &nbsp;&nbsp;
  <a href="https://buy.stripe.com/00w14n5NjgLDf3W53W6Na00" target="_blank" style="text-decoration:none;">
    <img src="https://img.shields.io/badge/Subscribe_Monthly-green?style=for-the-badge&logo=stripe&logoColor=white" alt="Monthly Subscription" />
  </a>
</p>

Simply click the button above to purchase a monthly or yearly license.

For licensing details or inquiries, please contact: loiczimm@gmail.com.

## Using a License with QMLib

To unlock the full features of QMLib, you need a valid license key and signature. Follow the steps below to set up your license.

---

### 1. Purchase a License

Click the **Subscribe** button above to purchase a license.
After completing the purchase, a license key will be sent to the email address you provided.

---

### 2. Generate a Signature

Using the license key, you need to generate a signature in your CMake build system. Here’s how:

```cmake
# Set the license key
set(LICENSE_KEY "<license_key>") # Replace <license_key> with your actual license key

# Call the validate_license function and store the result
validate_license("${LICENSE_KEY}" LICENSE_SIGNATURE)
```

### 3. Configure License in CMake
Add the license key and signature to your build definitions:

```cmake
# Add definitions for the key and signature
add_definitions(-DQMLIB_KEY="${LICENSE_KEY}")
add_definitions(-DQMLIB_SIGNATURE="${LICENSE_SIGNATURE}")
```

### 4. Use the License in C++ Code
Set up the license in your application code as follows:

```Cpp
#include <license/QMLib.h>

int main() {
   ...
   
   // Initialize the license
   QMLib::setLicense(QMLIB_KEY, QMLIB_SIGNATURE);

   ...
}
```
  
Ensure that the QMLib target is linked in your CMake configuration:

```cmake
target_link_libraries(your_target_name PRIVATE QMLib::QMLib)
```

By following these steps, your application will be properly licensed and ready to utilize the full capabilities of QMLib.

### Note on License Checks
All license checks with the server are performed only at compile time. The generated software does not perform any server pings or license checks at runtime. This ensures that the application operates independently without requiring an active internet connection after compilation.

By following these steps, your application will be properly licensed and ready to utilize the full capabilities of QMLib.

## System Requirements
- **Qt Version:** 6.7+  
- **CMake Version:** 3.21 or higher  
- **Supported Platforms:** Linux, macOS, Windows, iOS, Android, WearOS, watchOS, WebAssembly (with some module limitations).

## Contributing
This repository is for binary distribution only. If you’d like to contribute to QMLib examples or report issues, visit the [Examples Repository](https://github.com/zimmldev/qmlib-examples).

---

Thank you for using QMLib to power your QML applications!
