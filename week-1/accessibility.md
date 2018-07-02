# Accessibility
  # accessible navbar
our key areas of accessibility:
Keyboard accessible navigation – Keyboard accessible navigation is crazy helpful for people with dexterity issues.
Moving and clicking a mouse on a tiny 16×16 pixel icon can prove to be very difficult.

   Touch device capable – Users prefer visit the site through touch enabled devices, including phones, tablets, and even
   desktop computers.

   Mobile users with smaller screens – Given that most mobile devices are touch-enabled, this is still a different group
   of people due to the screen resolution.

   Assistive technology friendly – Users with sight disabilities rely on screen readers and other assistive technologies.
   We strive to keep this in mind when building pages.

   1.Color Contrast.
   2.Underlying.
   3.Font size.
  4.Other visual cues.
  5.Styling your skip links.
# accessible modal
 1.Semantic HTML:
This means using the correct HTML elements for their correct purpose as much as possible.
For example, a control button to play a video on your site could be marked up like this:
```<div>Play video</div>```


But as you'll see in greater detail later on, it makes much sense to use the correct element for the job:
```<button>Play video</button>```

 2. Managing focus:
   Focus determines where keyboard events go in the page at any given moment. For instance, if you focus a text input
   field and begin typing, the input field receives the keyboard events and displays the characters you type

3. Adding key handlers:
   In HTML, keyboard handlers may be triggered by keydown, keyup, or keypress events. It is also helpful to provide
   onclick handlers, which trigger the default action for the widget. For simple widgets, keyboard support may just
   provide support for the Enter key

4. Adding aria attributes:
   ARIA is a set of special accessibility attributes which can be added to any markup, but is especially suited to HTML.
   The role attribute defines a specific role for type of object (such as an article, alert, slider or a button).