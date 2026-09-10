# Modal

<img width="771" height="769" alt="modal-open" src="https://github.com/user-attachments/assets/79c88767-1880-4773-8c7b-9c573409b2a0" />

## installation
Put the `amodal.liquid` file into your theme `components` folder.

## Installation

In a `layout`, `template` or `snippet` file, add the `amodal` component.

```
{% component 'amodal' %}
```

To open a modal you should have a clickable element such as a `button` and set an `id` on it that the modal can `target`.

```
<button id="my-contact" class="btn">{{ 'Open contact form' | t:'default'  }}</button>
<a-modal target="my-contact" width="50em">   
  <h3>Contact form</h3>
  {% form 'contact' success:'Thank you for signing up!' error:'Form contains errors, please try again!' %}{% endform %}
  <p>We won't sell or share this information with anyone.</p>
</a-modal>
{% component 'amodal' %}
```

### Customisation
You pass configuration using html attributes on the `<a-modal ...>` tag.

* `width` of the modal window, default `30rem`
