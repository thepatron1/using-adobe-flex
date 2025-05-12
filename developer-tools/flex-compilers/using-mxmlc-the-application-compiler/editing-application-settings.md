# Editing application settings

The mxmlc compiler includes options to set the application's frame rate, size,
and script limits. By setting them when you compile your application, you do not
need to edit the HTML wrapper or the application's MXML file. You can override
these settings by using properties of the `<s:Application>` tag or properties of
the `<object>` and `<embed>` tags in the HTML wrapper.

The following command-line example sets default application properties:

    mxmlc -default-size 240 240 -default-frame-rate=24 -default-script-limits 5000 10 -- c:/myfiles/flex/misc/MainApp.mxml

For more information about the Application class, see
[Application containers](../../../building-the-user-interface/application-containers/index.md).

For more information about the HTML wrapper, see
[Creating a wrapper](../../../deploying-applications/creating-a-wrapper/index.md).
