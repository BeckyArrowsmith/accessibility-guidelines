#Accessibility guidelines

These guidelines should be followed by anyone designing, developing, testing or otherwise   Co-ops digital products and services. These guidelines are not essential for Alpha builds but be aware that you cannot test properly with users without them. Beta and onwards should most definitely follow these guidelines.

##But why?
>“The power of the Web is in its universality. Access by everyone regardless of disability is an essential aspect.”
Tim Berners-Lee, W3C Director and inventor of the World Wide Web

The Web is fundamentally designed to work for all people, regardless of any disability or access need. The Web should be accessible to people with a diverse range of hearing, movement, sight, and cognitive ability.

The impact of disability is radically changed on the Web because the Web, in it’s nature, removes barriers to communication and interaction that many people face in the physical world. However when digital products and services are badly designed, avoidable barriers to content are put in place.

## The Equality Act 2010
Since the Disability Discrimination Act 1995 came into force, website owned have been obligated to provide accessible digital products and servers to users with disabilities. These requirements were then merged into the [Equality Act 2010](http://www.legislation.gov.uk/ukpga/2010/15/contents) which was created to provide clarity.

#### Reasonable adjustments
Sections 20 and 29(7) of the Equality Act state that "reasonable adjustments" should be made to allow disabled people to use your services. In the case of imformation being provided:

> The steps which it is reasonable for [an information service provider] to have to take include steps for ensuring that in the circumstances concerned the information is provided in an accessible format.

**Section 20(6) of the Equality Act 2010**

The act also states this should be an ongoing task (not just considered once) and it should be anticipatory rather than reactive (7.27 and 7.21 respectively).

And of course, we want to make awesome stuff in general!

##So how do we do this?
Each standard is unambiguous and testable and guidelines for testing will be provided. Examples will be provided where possible.

####But before that…
Care should be taken during the design stage to ensure the service has no barriers to those with visual, hearing, cognitive or motor impairments. Testing is always best but there a number of things you can keep in mind:

##The absolute basics
These things are so simple they should be used anyway, without thought. They’re useful for anyone, regardless of disability.

####Alt Tags
These are used as descriptors for images. They should be concise and to the point.

Never use “image of…” - imagine (or test!) how annoying it would be for a screen reader to read those words out to a user over and over again. “Group of Co-op colleagues conducting their stand up” is a much better example than “an image of Co-op colleagues”.

Be aware of how screen readers read out acronyms. “a computer PSU” will be read out at “a computer sue” which will mean nothing to the user without some thought! Spacing between the letters of acronyms will result in them being read out correctly.

Don’t overthink your wording, think of it like a Tweet: you’re trying to get the most information out in the smallest number of characters.

If an image provides no contextual value and is simply for visual purposes be sure to provide an empty `alt=""` attribute, most screen readers may try to read out the entire image URL if there is no alt attribute at all!

####Title tags
Title tags are very similar to alt tags though they have a distinct differences. An alt tag is for alternate information, essentially, describing something. A title tag however is used to give extra information. Think of it as a type of tooltip. On most browsers they will actually render as a tooltip. 

<a href=“google.com” title=“Google Homepage”>Google</a> will show “Google Homepage” when hovering over the link.

It’s not essential to use a title tag on an image like it is an alt. However, on links, titles should always be used.

####Labelling form controls
Labelling form controls helps everyone better understand your form. A label should state the purpose of your control. A label can be hidden (if the purpose of the control is clear enough from the context) but not without using aria-label, title or hiding the label with CSS to support those with screen readers.

####No text in images
This will render your text invisible to both screen readers, those with images turned off/hidden and search engines.

####Group form controls within field sets
This will allow those using screen readers to get a grasp of the context of each grouping of controls. It will also allow the user to skip between field sets using tab targets.

####Legends
Each fieldset should have a <legend> to give context about each fieldset. This can be hidden with CSS.

####Input types
Appropriate input types will not only give additional context to an action but also utilise browser technologies such as tap to call.

*For example:*

`<a href=“tel:+440161123456” title=“Call Co-ops helpline”>Call helpline</a>`

Will allow the browser to send the number to a smart phones dialer. It will also enable the user to auto populate forms more easily, especially useful for users who have trouble typing.

####Tab index
Tab index essentially sets the order of ‘focusable’ elements. It allows the user to skip around the form using the tab key. it is set using a numeric value, see below:

* `<input tabindex=“-1”>` - the minus value indicates this is not to be ‘focusable’. This is useful for skip links.

* `<input tabindex=“0”>` - the first focused control when the tab hit is hit.

* `<input tabindex=“1”>` - and the second, and so on.

##WCAG guidelines
The Web Content Accessibility Guidelines, often abbreviated to WCAG, are a series of guidelines for improving web accessibility. Produced by the World Wide Web Consortium (W3C), the WCAG are the best means of making your website useful to all of your users.

###WCAG ‘basic’ guidelines (Level A)
These are what WCAG consider ‘basic’ guidelines. Links to the full documentation and a succinct explanation is provided. You will see some repetition from the above

####Provide text alternative for non-text content

Non-text content constitutes text within an image or video. This can’t be read by screen readers, search engines or those with images/videos turned off/hidden.
All examples of non-text text must have a text alternative.
Videos must have transcriptions, text in images must be reflected in alt/title tags.

####Logical structure

A logical order is best for semantics and screen reading applications.
Use HTML5 elements correctly and avoid floating things weirdly
Your pages pass [HTML5 validation](https://validator.w3.org/) and can screen reading software is able to navigate easily

####Sensory Characteristics

This essentially means you are using more than one indicator for explaining instructions.
“use the search bar on the right” is hard to understand by someone who doesn’t know what ‘right’ is. It’s important to use different indicators for instructions.
In the above example, an icon pointing towards right is an extra visual cue which is easily implementable to give more context to your action.

####Use of colour

Don’t highlight states only using colour. Use another indicator, such as text or an icon. An example could be a using an icon (such as a simple asterix) on a required field as well as the standard red text.

####Don’t play audio automatically

This is annoying for anyone!
Visually impaired users may struggle to see how to turn auto-play audio off
Those with physical disabilities may take longer to turn it off.

####Accessible by keyboard only
If a user wants to navigate your website just by using a keyboard they should be able to
Utilise tab targets to allow this. Aria roles can also help.
A user can skip between form sections and focus points just with their keyboard

####Time limits have user controls
Those with dexterity impairments may not be able to do your time sensitive task within the given time range.
A time limit should be able to be paused or cancelled to remove the pressure on the user.
A highly visible and accessible method for cancelling/pausing the time limit should be implemented.

####Provide user controls for moving content
A user should have the ability to pause/stop moving elements
In an module such as a carousel, the user should be allowed to stop the content from moving
The user can easily stop content from moving

####No content flashes more than three times per second
This is annoying for any user, but especially more confusing  for those with dyslexia. For those with epilepsy, this can be downright dangerous.
Flashing should be avoided where possible, in any case.
NOTHING should flash for more than three times per second

####Provide skip links
Skip links allow the user to skip to key sections, or landmarks, on the webpage.
These could include skip links to the header (“back to top” is a common example), or down to the footer.
Skip links to ‘big’ landmarks are available to the user.

####Every links purpose is clear from its context
A user should be able to get an idea of where a link will take them without clicking it
This can be done by providing good link text, and a title attribute for more context

####Clearly identify input errors
A user should be given information of what went wrong when entering incorrect data within an input
They should advised on how to fill it out corrected within the validation text
Input masks should be used to prevent errors in the first place
Input types should be thought about (can this dropdown be replaced by a simple text box?)

##WCAG ‘intermediate’ guidelines (Level AA)
These are what WCAG consider ‘intermediate’ guidelines. Links to the full documentation and a succinct explanation is provided.

####Live videos have captions
Deaf or hard of hearing people should be allowed to watch real time presentation via the use of captions. They should be available via the audio track.
Users have access to audio descriptions for video content
Captions should describe the content for the visually impaired or those unable to see access video.

####Contrast ratio between text and background is at least 4:5:1
Contrast should be designed in a way that colour is not a key factor so that users with colour vision deficits can see your content.

####Text can be resized to 200% without loss of content or function
Browser magnifying controls should work properly and allow the user to screenreader text at their chosen size without the need for a 3rd party program.

####Ensure keyboard focus is visible and clear
A user should understand which element amongst a multiple elements has the keyboard focus.

####Use menus consistently
Menu content, form and function should not change anywhere on the website.

####Use icons and buttons consistently
Button styles, colours and sizes should not change throughout the website.

##WCAG Advanced’ guidelines (Level AAA)
These are what WCAG consider ‘advanced’ guidelines. Links to the full documentation and a succinct explanation is provided.

####Provide sign language translations for videos
Self explanatory. An optional video track with signing should be provided.

####Provide extended audio description for videos
An extended audio description includes description about actions, characters and scene changes.

####Contrast ratio between text and background is at least 7:1
More contrast compared to the AA rating.

####Accessible by keyboard only, without exceptions
Tab index in implemented in such a way that entire pages are keyboard navigable only.

####No time limits
There are no time limits whatsoever in the service.

####Save user data when re-authenticating
User data is cached to enable ease of relog.

####Explain any abbreviations
All abbreviations are explained within the same viewport as the actual abbreviation.

####Users with nine years of education can read your content (year 9)
Language should be inclusive to all.

####Explain any words that are hard to pronounce
Self explanatory.

##Testing
You can test yourself using online services, though be aware that these will pick up 25% of issues at best: use your user researchers!

The most common of these services include:

* [WAVE](http://wave.webaim.org/)
* [Tenon](https://tenon.io/)
* [HTML_sniffer](https://www.squizlabs.com/general/html-codesniffer)

You can also check out [W3Cs list of web accessibility tools](https://www.w3.org/WAI/ER/tools/?q=wcag-20-w3c-web-content-accessibility-guidelines-20).


##ARIA roles
WAI-ARIA is a specification defining support for accessible web apps. It defines markup extensions (mostly as attributes on HTML5 elements), which can be used by developers to provide additional information about the semantics of the various elements to assistive technologies like screen readers. For ARIA to work, the HTTP user agent that interprets the markup needs to support ARIA, but the spec is created in such a way, as to allow down-level user agents to ignore the ARIA-specific markup safely without affecting the web app's functionality. Some practical examples

— own markup of examples here —

##Screen Readers
Screen readers are software designed to allow blind or visually impaired users do a variety of things, though mainly to read the text displayed on the screen via a speech synthesiser. A screen reader will essentially sit between the OS and its applications and the user. The user can use a number of ways to communicate with this software, the main way being keyboard commands which allows the user to. The user can skip around a webpage or app and instruct the screen reading software to read out what they require.

**Some popular examples of screen readers include:**

[Apple Voiceover](https://www.w3.org/WAI/ER/tools/?q=wcag-20-w3c-web-content-accessibility-guidelines-20)
* Features Alex, a voice synthesiser that includes a ‘breath’ between words to make it more human-like.

* Gestures can be used for more information about a highlighted part of the page, help the user skip to another page of the page or a different page entirely.

* “The Rotor” is used to switch between options easily, like an actual dial. This lowers the barrier of entry as new gestures don’t have to be used.

* This is of course only accessible on Apple devices.

[JAWS] (http://www.freedomscientific.com/Products/Blindness/JAWS) (Job Access With Speech)
* Usage figures are dropping for JAWS, quite possibility because of it’s aging tech and high price compared to other free, high quality alternatives. Usage has dropped from 63.9% of users deeming they use it often to 43.7%.

[NVDA](http://www.freedomscientific.com/Products/Blindness/JAWS) (NonVisual Desktop Access)
* NVDA is developed by two visually impaired friends who founded the non-profit organisation NV access to support the development of the NVDA screen reader.

* NVDA is open source software, which means the code is accessible to anyone. This enables translators and developers around the world to continually contribute to its expansion and improvement.

#Useful links

* [ARIA Practical Examples](http://heydonworks.com/practical_aria_examples/)
* [Creating Accessible PDFs](https://www.gov.uk/service-manual/user-centred-design/resources/creating-accessible-PDFs.html)
* [Disability Language and Behavior](http://www.disabilitysheffield.org.uk/admin/resources/disability-terminology-and-etiquette.pdf)
* [GDS: accessibility blog](https://accessibility.blog.gov.uk/)
* [GDS: Making your service accessible: an introduction](https://www.gov.uk/service-manual/helping-people-to-use-your-service/making-your-service-accessible-an-introduction)
* [Web Accessibility Evaluation Tools List](https://www.w3.org/WAI/ER/tools/?q=wcag-20-w3c-web-content-accessibility-guidelines-20)


**Todo:**
* how to utilise in design process vs development
* disabilities that "fight". visual impairment high contract vs dyslexia low contrast reading
* Add links back into WCAG section headings, like the Google doc

#Wanna get involved?
I've gone through all the techy stuff but need your help!

This document was originally for the Wills team to nail form semantics and what not. I'd really like it to become a big living document for the entirety of the Co-op but I can't do that alone any time soon. If you have any input please Slack me, email me or do a pull request.

Any submission to the document will be massively appreciated, even if it's just a task for the todo list.
