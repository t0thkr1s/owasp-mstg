#MASVS-PLATFORM-3 

Check the app for usage of certain APIs and attributed typically used to protect against overlay attacks as well as check the Android version that app is targeting.

Check the app for the following methods and attributes:

- Override `onFilterTouchEventForSecurity` for more fine-grained control and to implement a custom security policy for views.
- Set the layout attribute `android:filterTouchesWhenObscured` to true or call setFilterTouchesWhenObscured`.
- Check FLAG_WINDOW_IS_OBSCURED (since API level 9) or FLAG_WINDOW_IS_PARTIALLY_OBSCURED (starting on API level 29).

- [ ] Check