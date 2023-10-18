# PLEASE NOTE THIS MIMIK CORE CLIENT LIBRARY IS NO LONGER BEING MAINTENAINED
# THE NEXT GENERATION CLIENT LIBRARY IS AVAILABLE HERE: https://github.com/mimikgit/cocoapod-EdgeCore#

#
# MIMIKEdgeClientCore

 MIMIKEdgeClientCore library can help you interact with mimik core services with the following APIs:
 
## Core Services

### Environment

 * `setLoggingLevel`
 * `selectBackend`
 * `selectedBackend`
 * `healthCheck`
 * `manuallySelectedBackend`
 * `applicationBackend`
 * `forceDefaultBackendSelection`
 * `defaultBackend`
 * `workingDirectory`
 * `edgeEngineWorkingDirectory`

### edgeEngine controls
 
 * `deployMicroservice`
 * `undeployMicroservice`
 * `undeployMicroserviceComponent`
 * `deployedMicroservices`
 * `verifyDeployedMicroserviceMatching`
 * `deployedMicroserviceImages`
 * `deployedMicroserviceImage`
 * `deployedMicroserviceContainers`
 * `deployedMicroserviceContainer`
 * `updateMicroservice`
 * `updateMicroserviceConfig`
 * `edgeEngineIdToken`
 * `edgeEngineInfo`
 * `externalEdgeEngineIsRunning`
 * `edgeEngineUrlComponents`
 * `edgeEngineUrlString`
 * `edgeEngineWorkingDirectory`
 * `edgeEngineWebSocketServiceLink`
 
### External edgeEngine controls

 * `activateExternalEdgeEngine`
 * `deactivateExternalEdgeEngine`
 * `externalEdgeEngineActivated`

### Backend Calls
 * `callBackend`

### Response Validation
 
 * `responseJSON`
 * `responseData`
 * `responsePagingInfo`
 * `responseError`

### UTType Documents
 * `uttypeFor`
 * `fileExtensionFor`
 * `mimeTypeFor`

 
### Content Services
 * `uploadContent`
 * `downloadContent`
 * `downloadImageContent`
 * `exportVideo`

## Authentication Services
 
 * `authenticateDeveloperAccess`
 * `authenticateEdgeEngineAccess`
 * `validateEdgeEngineAccess`
 * `authenticateUserAccess`
 * `deleteAccount`
 * `accountInformation`
 * `supportedAuthenticationScopes`

 Please see the in-code documentation in Xcode for more details.

## edgeEngine Framework 
 
For adding edgeEngine framework to your project please see: [MIMIKEdgeClientEngine](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientEngine)

## Supported Platforms, Targets
* `iOS Devices running iOS 15+`
* `iOS Simulators running iOS 15+`
* `iOS Mac Catalyst running macOS 12.0`

## Requirements
```
iOS 15.0+
```

## Installation

To install it, simply add the following lines to your Podfile:


```swift
platform :ios, '15.0'
source 'https://github.com/CocoaPods/Specs.git'
source 'https://github.com/mimikgit/cocoapod-edge-specs.git'

use_frameworks!
inhibit_all_warnings!

def mimik
  pod 'MIMIKEdgeClientCore'
end

target '{target}' do
  mimik()
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['ENABLE_BITCODE'] = 'NO'
      config.build_settings['VALID_ARCHS'] = '$(ARCHS_STANDARD_64_BIT)'
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '15.0'
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'
    end
  end
end
```


## Tutorial

Visit this [tutorial](https://devdocs.mimik.com/tutorials/03-index) to learn more about the mimik client library and how to integrate it into your iOS project.

## mimik client and service libraries

Don't forget to checkout all mimik client and service libraries [available on Github](https://github.com/search?q=cocoapod-MIMIKEdgeClient)

Direct links:
 
 * [MIMIKEdgeClientCore](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientCore)
 * [MIMIKEdgeClientEngine](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientEngine)
 * [MIMIKEdgeClientUser](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientUser)

## Author

mimik

```
https://github.com/mimikgit/cocoapod-MIMIKEdgeClientCore
```

## License

The aforementioned mimik client and service libraries are available under the MIT license. See the LICENSE file for more information.
