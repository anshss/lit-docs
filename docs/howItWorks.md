---
sidebar_position: 3
---

# How does the LIT protocol work?

## Static Content - Encrypting / locking

This SDK will encrypt your content, and upload your conditions for decryption to each LIT node. When someone wants to access the content, the SDK will request a message signature from the user's wallet that proves that they own the NFT associated with the content to each LIT node. The LIT nodes will then send down the decryption shares and the SDK will combine them and decrypt the content.

## Dynamic Content - Authorizing access to a resource via JWT

This SDK has the ability to create the authorization conditions for a given resource and store them with the LIT nodes. When someone requests a network signature because they are trying to access a resource (typically a server that serves some dynamic content), the SDK will request a message signature from the user's wallet that proves that they own the NFT associated with the resource to each LIT node. The LIT nodes will each verify that the user owns the NFT, sign the JWT to create a signature share, then send down that signature share. The SDK will combine the signature shares to obtain a signed JWT which can be presented to the resource to authenticate and authorize the user.