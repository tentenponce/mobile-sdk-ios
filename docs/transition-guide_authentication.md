![Fastfill & Netverify](images/authentication.jpg)

# Transition guide for Authentication SDK

This section only covers the breaking technical changes that should be considered when updating from the previous version.

## 3.4.2
* A new delegate `authenticationScanViewController:shouldRequireUserConsentWithURL:` was added to [`AuthenticationScanViewControllerDelegate`](https://jumio.github.io/Mobile-SDK-IOS_pilot/NetverifyFace/Protocols/AuthenticationScanViewControllerDelegate.html)
* A new method `userConsentGiven:` was added to [`AuthenticationScanViewController`](https://jumio.github.io/Mobile-SDK-IOS_pilot/NetverifyFace/Classes/AuthenticationScanViewController.html)

## 3.4.1
No backward incompatible changes.

## 3.4.0
No backward incompatible changes.

## 3.3.1
No backward incompatible changes.

## 3.3.0
No backward incompatible changes.

## 3.2.0

#### Custom-UI handling
`authenticationScanViewController:shouldDisplayHelpWithText:animationView:` was extended to [`authenticationScanViewController:shouldDisplayHelpWithText:animationView:forReason:`](https://jumio.github.io/mobile-sdk-ios/NetverifyFace/Protocols/AuthenticationScanViewControllerDelegate.html#/c:objc(pl)AuthenticationScanViewControllerDelegate(im)authenticationScanViewController:shouldDisplayHelpWithText:animationView:forReason:) to return the `JumioZoomRetryReason`

## 3.1.2
No backward incompatible changes.

## 3.1.1
No backward incompatible changes.

## 3.1.0

#### NavigationBar customization
`UINavigationBar+AuthenticationAppearance.h` was renamed to `UINavigationBar+JumioAppearance.h` and moved to JumioCore.framework</br>
`AuthenticationNavigationBarTitleImageView` was renamed to [`JumioNavigationBarTitleImageView`](https://jumio.github.io/Mobile-SDK-IOS_pilot/NetverifyFace/Classes/JumioNavigationBarTitleImageView.html) and moved to JumioCore.framework

#### Custom-UI handling
Please see [Custom-UI for Authentication](https://github.com/Jumio/mobile-sdk-ios/blob/master/docs/integration_authentication.md#custom-ui) 
`authenticationScanViewControllerDidStartBiometricAnalysis:` - display loading activity while biometric data is being analysed
`authenticationScanViewController:shouldDisplayHelpWithText:animationView:` - Display a help text and animated view that is provided based on the problematic situation the user was facing and call `retryScan` on the `authenticationScanViewController` on user confirmation.
`authenticationScanViewController:didDetermineRecoverableError:` - Display the error message to the user and call `retryAfterError` on the `authenticationScanViewController` on user confirmation.

`authenticationController:didFinishInitializingScanViewController:` was adapted to return a `AuthenticationScanViewController` instance instead UIViewController.

`AuthenticationScanViewController` provides a property `customOverlayLayer` to add subviews on top as well as mechanism to retry in help/error state or cancel.

#### Changes to device information
`JMDeviceInfo` class has been renamed to `JumioDeviceInfo`

## 3.0.0
Introduction of the Authentication product
https://github.com/Jumio/mobile-sdk-ios/blob/master/docs/integration_authentication.md#callback
