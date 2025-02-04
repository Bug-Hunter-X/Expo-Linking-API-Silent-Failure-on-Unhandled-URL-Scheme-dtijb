# Expo Linking API Silent Failure on Unhandled URL Scheme

This repository demonstrates a subtle bug in the Expo `Linking` API. When attempting to open a URL with an unsupported scheme, the API silently fails without providing any error or feedback to the developer.  This can lead to significant debugging challenges.

## Bug Description
The issue lies in the lack of informative error handling when a URL with an unsupported or unregistered custom scheme is passed to `Linking.openURL`.  Instead of an error, the function simply returns without any indication of failure. This makes it difficult to identify why a URL isn't opening.

## Steps to Reproduce
1. Clone this repository.
2. Run the `unhandledURLSchemeBug.js` file.
3. Observe that the application attempts to open a URL with a custom scheme. No error or feedback is provided to indicate failure. 
4. Run `unhandledURLSchemeSolution.js` to see the solution implemented.

## Solution
The solution involves adding robust error handling to check the result of `Linking.openURL`.  The provided `unhandledURLSchemeSolution.js` demonstrates how to handle potential failures gracefully. 