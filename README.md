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

### Customisation
You pass configuration using html attributes on the `<a-modal ...>` tag.

* `width` of the modal window, default `max-content`
