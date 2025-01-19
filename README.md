# Silent Failure of Expo's useLocalAuthentication Hook on Android

This repository demonstrates a bug in Expo's `useLocalAuthentication` hook on Android where authentication can fail silently, without providing any error messages.  This makes debugging extremely challenging. The example includes a buggy implementation and a solution to improve error handling.

## Bug
The original code uses `useLocalAuthentication` without proper error handling.  If authentication fails for any reason (e.g., fingerprint sensor issue, incorrect configuration), no error is thrown or logged, making it difficult to determine the cause.

## Solution
The solution introduces more robust error handling by checking the result object from `useLocalAuthentication` for any errors. If an error occurs, it logs the error to the console, which provides valuable debugging information.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run the app on an Android emulator or device.
4. Attempt authentication.  If it fails silently in the original `bug.js` file, observe that the solution in `bugSolution.js` provides more context.