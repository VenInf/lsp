Hi Fendor, sorry for taking so long, now I have a little bit of progress on the issue, see here: https://github.com/VenInf/lsp/tree/consistent-registration-583

Now thinking on how it's better to provide the `StaticHandle` to the `ServerDefinition` , while getting the correct `ServerCapabilities`. I came up with the following:

Users register using methods `notificationHandler`/`requestHandler` like they used to, but now they also have to provide the capabilities related to the handler.

After that, in the `initializeRequestHandler`,  we compute both `Handles` and `ServerCapabilities`