<p align="center">
<a href="http://kitura.io/">
<img src="https://raw.githubusercontent.com/IBM-Swift/Kitura/master/Sources/Kitura/resources/kitura-bird.svg?sanitize=true" height="100" alt="Kitura">
</a>
</p>


<p align="center">
<a href="http://www.kitura.io/">
<img src="https://img.shields.io/badge/docs-kitura.io-1FBCE4.svg" alt="Docs">
</a>
<a href="https://travis-ci.org/IBM-Swift/Kitura-net">
<img src="https://travis-ci.org/IBM-Swift/KituraContracts.svg?branch=master" alt="Build Status - Master">
</a>
<img src="https://img.shields.io/badge/os-Mac%20OS%20X-green.svg?style=flat" alt="Mac OS X">
<img src="https://img.shields.io/badge/os-linux-green.svg?style=flat" alt="Linux">
<img src="https://img.shields.io/badge/license-Apache2-blue.svg?style=flat" alt="Apache 2">
<a href="http://swift-at-ibm-slack.mybluemix.net/">
<img src="http://swift-at-ibm-slack.mybluemix.net/badge.svg" alt="Slack Status">
</a>
</p>

# KituraContracts

## Summary

KituraContracts is a library containing type definitions shared by client (e.g. [KituraKit](https://ibm-swift.github.io/KituraKit/)) and server (e.g. [Kitura](https://ibm-swift.github.io/Kitura)) code. These shared type definitions include [Codable Closure Aliases](https://ibm-swift.github.io/KituraContracts/Typealiases.html), [RequestError](https://ibm-swift.github.io/KituraContracts/Structs/RequestError.html), [Identifier Protocol](https://ibm-swift.github.io/KituraContracts/Protocols/Identifier.html#/s:15KituraContracts10IdentifierP5valueSSv) and [Extensions](https://ibm-swift.github.io/KituraContracts/Extensions.html#/s:SS) to String and Int, which add conformity to the Identifier protocol.

### Example Code Sample: ###
````swift
public struct User: Codable {
...
}

router.post("/users") { (user: User, respondWith: (User?, RequestError?) -> Void) in

    if databaseConnectionIsOk {
        ...
        //If no errors occured and you have a User you can just respond with the user by passing nil as the 'RequestError?' value.
        respondWith(user, nil)
    } else {
        ...
        //If there has been an error you can use the respondWith call to respond with an appropiate error and passing nil for the User?.
        respondWith(nil, .internalServerError)
    }
}
````

## Swift version
The 0.0.x releases were tested on macOS and Linux using the Swift 4.0.2 binary. Please note that this is the default version of Swift that is include in [Xcode 9.1](https://developer.apple.com/xcode/).

## Community

We love to talk server-side Swift and Kitura. Join our [Slack](http://swift-at-ibm-slack.mybluemix.net/) to meet the team!
