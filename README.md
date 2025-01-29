# Mobile-Automation--MAESTRO

## Overview
This project provides a complete mobile automation testing framework for Android apps using **Maestro**. The script automates a series of actions for logging into a mobile app, adding items to the cart, filling out checkout details, and verifying the order completion.

The framework leverages **Maestro Studio** for visual debugging and simplifies mobile app testing, ensuring that tasks like login, checkout, and item selection are tested with minimal setup.

## Prerequisites

1. **Maestro**: Follow the [Maestro installation guide](https://docs.maestro.mobile) to set up Maestro on your system.
2. **Android Emulator or Device**: Ensure you have an Android emulator set up via **Android Studio** or a physical Android device connected.

## Steps to Set Up and Run Tests

### 1. Clone the Repository

Clone this repository to your local machine:
```bash
git clone https://github.com/your-username/Mobile-Automation--MAESTRO.git
cd Mobile-Automation--MAESTRO
```

### 2. Configure the App ID

Update the `appId` field in the script with the correct package name for your app:
```yaml
appId: com.swaglabsmobileapp # Replace with your app's package name
```

### 3. Run the Test

To run the test, use the following command in the terminal:
```bash
maestro test smoke_test.yaml
```

### 4. Use Maestro Studio for Visual Debugging

**Maestro Studio** provides a user-friendly interface to help you:

- **Inspect Elements**: Identify and interact with UI elements visually.
- **Debug Locators**: Test your element locators directly in the visual interface.
- **Modify Tests**: Easily modify test flows and commands using a GUI without writing code.

Follow these steps to use **Maestro Studio** effectively:

1. Launch **Maestro Studio**.
2. Connect your device or emulator to **Maestro Studio**.
3. Start a new session, select the app you wish to test, and use the **UI Inspector** to explore elements.
4. Use the **Visual Flow Builder** to create and edit test cases with drag-and-drop actions.

### 5. View the Results

Maestro will automatically display the results of the test execution in the terminal. In **Maestro Studio**, you can also monitor test execution in real-time and inspect any failures visually.

## Best Practices

To ensure reliable and maintainable tests, the following best practices are implemented:

### 1. **Use Explicit Waits**

Instead of relying on fixed wait times, the script uses explicit waits and selectors like `extendedWaitUntil` to ensure elements are visible before interacting with them. This reduces flakiness and ensures the app is ready for the next action.

### 2. **Efficient Element Locators**

Implemented a combination of text selectors, regex selectors, and relative positioning to target UI elements accurately. This helps avoid brittle locators that break easily with minor changes in the UI.

### 3. **Modular Test Cases**

The test cases are modular, each focusing on a specific aspect of the app (e.g., login, checkout). This makes it easier to isolate issues and reuse test components for future testing scenarios.

### 4. **Randomized Inputs**

For more robust testing, some inputs (like the postal code) are randomized. This ensures that the test covers a wider variety of input cases and isn’t limited to hardcoded values.

### 5. **Environment Configurations**

The test setup is designed to be environment-agnostic, meaning that the configuration for different devices or platforms can be easily switched without modifying the test code.

### 6. **Test Assertions**

After key actions like logging in and completing checkout, assertion for the presence of specific elements has been implemented (e.g., product listings, confirmation messages) to verify the expected outcome.

### 7. **Comprehensive Error Handling**

The script includes error handling techniques like `assertVisible` and custom wait times to handle any issues related to loading elements or interactions with the app.

## Troubleshooting

- **App Installation**: Ensure the app is correctly installed on the emulator or device. You can verify this using `adb devices` or opening the app manually.
- **App ID**: Double-check the `appId` in the script to match the package name of the app.
- **Element Selectors**: If an element is not found, use the Maestro studio to inspect elements and debug locators.
- **Emulator Issues**: If the emulator is not detected, ensure it’s running properly and that the environment variables are set correctly.

## Conclusion

This project provides a simple yet powerful framework to automate mobile app testing using **Maestro**. By leveraging **Maestro Studio** for visual debugging and following best practices, you can efficiently test and troubleshoot Android applications with minimal setup.

## Author: Louis Takow
