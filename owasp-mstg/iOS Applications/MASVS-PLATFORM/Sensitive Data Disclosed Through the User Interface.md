#MASVS-PLATFORM-3 

**Storyboard** In the iOS project's storyboard, navigate to the configuration options for the text field that takes sensitive data. Make sure that the option "Secure Text Entry" is selected. If this option is activated, dots are shown in the text field in place of the text input.

**Source Code** If the text field is defined in the source code, make sure that the option `isSecureTextEntry` is set to "true". This option obscures the text input by showing dots.

- [ ] Check