# Day - 1(drum-kit)

## New concepts
1. learned about <kbd> tag.
2. learned about data-key attr
3. attribute selector can be used in js too, eg (`audio[keyCode = "65"]`) this will select audio element with keyCode 65.

## How to?
1. We look for any keyDown event and console.log that event.
2. Then we use data-key attr. We gave all audio this attr, so we select audio with attr data-key. Then console.log that audio
3. Now we use audio.play() to make that audio play. Then to handle consecutive clicks, we set audio.currentTime to 0 every time keyDown occurs.
4. Now we need to add styles, so on keyDown we grab key with data-key attr and use key.classList.add('playing')
5. But problem is we also need to remove styles once and add it again when clicked. Adding is done now we need to remove.
6. we use transitionend callback, we grab all keys using querySelectorAll(returns nodeList, more about this in later videos). Then we use forEach loop to add an eventlistener to all keys one by one.
7. The call back to this is remoeveStyles, event returned by transitionend cb are properties transitioned. one of them here is transform. we stop execution if e.propertyname !== transform. Else we remove class playing by this.classList.remove('playing')