# Modal

<img width="771" height="769" alt="modal-open" src="https://github.com/user-attachments/assets/79c88767-1880-4773-8c7b-9c573409b2a0" />

## Installation

Put the `amodal.liquid` file into your theme `components` folder.

In a `layout`, `template` or `snippet` file, add the `amodal` component.

```
{% component 'amodal' %}
```

To open a modal you should have a clickable element such as a `button` and set an `id` on it that the modal can `target`.
```
<button id="my-contact" class="btn">{{ 'Open contact form' | t }}</button>
<a-modal target="my-contact">   
  <h3>{{'Contact form' | t}}</h3>
  {% form 'contact' success:'Thank you for contacting us!' error:'Form contains errors, please try again!' %}
  {% endform %}
  <p>{{"We won't sell or share this information with anyone" |t}}</p>
</a-modal>
{% component 'amodal' %}
```

> You can have multiple `a-modal`s per page, just add links or buttons that triggers them.

## effects
To add effects when the dialog opens or closes there is a couple of predefined effects you may use and combine.
* fadein - fades in from opacity 0 -> 1
* fadeout - fades out to opacity 0
* popup - scales up from 0.5 -> 1
* popout - scales up to 1.2 and opacity 0
* popin - scales down to 0.8 and opacity 0

You set the transition timing using the `timing` attribute.

### popup dialog with popout effect
```
button id="my-contact" class="btn">{{ 'Open contact form' | t }}</button>
<a-modal target="my-contact" effect="popup popout" timing="0.4s">   
  <h3>{{'Contact form' | t}}</h3>
  {% form 'contact' success:'Thank you for contacting us!' error:'Form contains errors, please try again!' %}
  {% endform %}
  <p>{{"We won't sell or share this information with anyone" |t}}</p>
</a-modal>
{% component 'amodal' %}
```


### Customisation
You pass configuration using html attributes on the `<a-modal ...>` tag.

* `width` of the modal, default `max-content`
* `top` margin
* `bottom` margin
* `left` margin
* `right` margin
* `align` content alignment,`start`, `center`,`end`, default `center`
* `padding` padding content, default `1rem`
* `gap` content item gap, default `0.25rem`
* `shadow` modal dialog shadow, default `0 19px 38px rgb(0 0 0 / 12%), 0 15px 12px rgb(0 0 0 / 22%)`
* `backdrop` color, default `rgb(0 0 0 / 70%)`
* `effect` transitions, `fadein`, `fadeout`, `popup`, `popout`, `popin`, default none.
* `timing` transitioning timing, default `0.3s` 
