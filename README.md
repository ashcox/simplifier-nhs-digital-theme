# simplifier-nhs-digital-theme

An NHS Digital theme for the Firely Simplifier product.

## Background

This theme has been created by NHS Digital for use with Implementation Guides on the Simplifier product provided by Firely.

[https://simplifier.net/organization/nhsdigital](https://simplifier.net/organization/nhsdigital)

---

## Installation

Add the `NHSDigitalStyle` directory to your Simplifier project and select the theme within the Simplifier Implementation Guide editor settings.

---

## How it works

Implementation guides can be written as normal and the theme will apply the NHS Digital styles and palette automatically when rendering the guide.

Some elements (such as callout-boxes) require HTML to be written.

For example

```html
<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6">
  <strong>Hi there!</strong> I am a light-blue box.
</div>
```

For more information, please review the documentation NHS Digital design framework documentation.

[https://dbs1dgg3cdf4v.cloudfront.net/](https://dbs1dgg3cdf4v.cloudfront.net/)

### A note on tables

Tables can still be written using markdown; however, writing them in HTML will be required to make them responsive or to turn off sorting.

For example:

```html
<table data-responsive>
  <!-- remove the 'data-responsive' attribute if you don't want a responsive table -->
  <thead>
    <tr>
      <th data-no-sort>Don't sort me</th>
      <th>You can sort me</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>*</td>
      <td>A</td>
    </tr>
    <tr>
      <td>*</td>
      <td>B</td>
    </tr>
    <tr>
      <td>*</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
```

### Code snippets

Existing NHS Digital guides already have a code snippet viewer - this will work and can be used as normal; however, to use the new viewer - use the following.

**Important**

Ensure that the `href` and `id` components in each block are different (e.g. `-1`, `-2`, `-3` etc.) if you have multiple code snippet viewers on the same page, otherwise it will render the same code snippet. It is using bootstrap three to swap out the views.

```html
<!--// start of code snippet -->
<div>
  <ul class="nav nav-tabs" role="tablist">
    <li role="presentation" class="active">
      <a href="#xml-1" aria-controls="xml" role="tab" data-toggle="tab">XML</a>
      <!-- href of xml-1 -->
    </li>
    <li role="presentation">
      <a href="#json-1" aria-controls="json" role="tab" data-toggle="tab"
        >JSON</a
      >
      <!-- href of json-1 -->
    </li>
    <li role="presentation">
      <a href="#table-1" aria-controls="table" role="tab" data-toggle="tab"
        >Table</a
      >
      <!-- href of table-1 -->
    </li>
    <li role="presentation">
      <a href="#tree-1" aria-controls="tree" role="tab" data-toggle="tab"
        >Tree</a
      >
      <!-- href of tree-1 -->
    </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="xml-1">
      <!-- id of xml-1 -->
      {{xml:example-bundle-med-request-inpatient-resupply-anne-teak}}
    </div>
    <div role="tabpanel" class="tab-pane" id="json-1">
      <!-- id of json-1 -->
      {{json:example-bundle-med-request-inpatient-resupply-anne-teak}}
    </div>
    <div role="tabpanel" class="tab-pane" id="table-1">
      <!-- id of table-1 -->
      {{table:example-bundle-med-request-inpatient-resupply-anne-teak}}
    </div>
    <div role="tabpanel" class="tab-pane" id="tree-1">
      <!-- id of tree-1 -->
      {{tree:example-bundle-med-request-inpatient-resupply-anne-teak}}
    </div>
  </div>
</div>
<!--// end of code snippet -->
```

#### Rendering profiles

This can be done using a similar method as a code snippet (explained above):

```html
<!--// start of code snippet -->
<div>
  <ul class="nav nav-tabs" role="tablist">
    <li role="presentation" class="active">
      <a href="#profile-3" role="tab" data-toggle="tab">Profile</a>
    </li>
    <li role="presentation">
      <a href="#dictionary-3" role="tab" data-toggle="tab">Dictionary</a>
    </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet">
    <div role="tabpanel" class="tab-pane active" id="profile-3">
      {{tree:ukcore-v2/ukcoremedicationstatement, snapshot}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-3">
      {{dict:ukcore-v2/ukcoremedicationstatement}}
    </div>
  </div>
</div>
<!--// end of code snippet -->
```

---

## Contributing

Please create a feature branch and request a merge into the the `develop` branch. Use the `master` branch for production releases.

---

## Further reading

This is theme is a work in progress and doesn't currently use all of the NHS-Digital branding.

The Simplifier product provided by Firely uses the bootstrap front-end development framework under the hood, which we are unable to remove.

We harness jQuery on page render to swap out or style individual elements.
