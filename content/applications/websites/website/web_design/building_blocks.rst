:show-content:

===============
Building blocks
===============

Design website pages by :ref:`dragging and dropping building blocks <website/building_blocks/add>`,
then :ref:`arrange <website/building_blocks/move_duplicate_delete>` and :ref:`edit
<website/building_blocks/edit>` them to fit your content and layout needs. It is also possible to
create :ref:`custom building blocks <website/building_blocks/custom>` or :ref:`anchor links
<website/building_blocks/anchor>`.

Building blocks can be added and customized using the website editor. To open it, go to the
relevant page and click :guilabel:`Edit` in the upper-right corner.

.. seealso::
   `Odoo Tutorial: Design your website: text and colors <https://www.odoo.com/slides/slide/design-your-website-text-and-colors-6930?fullscreen=1>`_

.. _website/building_blocks/add:

Add a building block
====================

To add a building block to a :doc:`website page <../structure/pages>`, access the page, then drag
and drop the desired building block from the :icon:`fa-plus` :guilabel:`Blocks` tab to the
appropriate location.

Two types of building blocks are available:

- Categorical building blocks provide templates for different content categories.
- :guilabel:`Inner Content` building blocks allow for adding elements, such as :ref:`videos
  <website/elements/videos>`, :ref:`images <website/elements/images>`, :ref:`buttons
  <website/elements/buttons>`, and more, to pre-existing categorical blocks as well as :doc:`headers
  and footers <../structure/header_footer>`.

When adding a categorical block, a pop-up window appears, allowing you to choose from multiple
templates for different categories. Once the block is placed, drag and drop :guilabel:`Inner
Content` blocks into it.

.. tip::
   - Use the search bar in the :guilabel:`Insert a block` pop-up window to quickly find a specific
     block.

     .. image:: building_blocks/insert-a-block.png
        :alt: Pop-up block selection
        :scale: 75%

   - Building blocks can also be added to the login page. To access it, navigate to the website's
     homepage, add `/web/login` to the URL, and press `Enter`.

.. note::
   Some building blocks require their corresponding application or module to be installed (e.g.,
   the **Appointments** app for the :guilabel:`Appointments` block).

.. example::
   Use the :guilabel:`Social Media` :guilabel:`Inner Content` building block to display links to
   your social media accounts. Click :guilabel:`Add New Social Network` to add a platform, and
   :icon:`fa-minus` (:guilabel:`Remove link`) to remove it. You can also edit the account URLs.

   .. image:: building_blocks/social-media-inner-content-block.png
      :alt: Social Media inner content block
      :scale: 75%

.. _website/building_blocks/form:

Form
----

The :guilabel:`Form` block is used to collect information from website visitors and, if applicable,
create records in your database. To add a form to a website page, drag and drop the
:guilabel:`Contact & Forms` category block, then select a block in the popup.

.. image:: building_blocks/form-block.png
   :alt: Example of a form block

.. _website/building_blocks/action:

Action
~~~~~~

By default, when the form is submitted, an email containing the information entered by the visitor
is automatically sent. Depending on the apps installed on your database, additional actions that can
automatically create records may become available. To choose a different action, click
:guilabel:`Edit`, click the form, navigate to the :guilabel:`Style` tab, and select the desired
:guilabel:`Action`:

- :guilabel:`Apply for a Job` (:doc:`Recruitment </applications/hr/recruitment>`)
- :guilabel:`Create a Customer` (:doc:`eCommerce <../../ecommerce>`)
- :guilabel:`Create a Ticket` (:doc:`Helpdesk </applications/services/helpdesk>`)
- :guilabel:`Create an Opportunity` (:doc:`CRM </applications/sales/crm>`)
- :guilabel:`Subscribe to Newsletter` (:doc:`Email Marketing </applications/marketing/email_marketing>`)
- :guilabel:`Create a Task` (:doc:`Project </applications/services/project>`)
- :guilabel:`More models`: to generate other types of records

By default, submitting the form redirects visitors to a *Thank you* page. Use the :guilabel:`URL`
field to send them to a different page. Alternatively, you can choose not to redirect and keep
them on the form's page by selecting :guilabel:`Nothing` or :guilabel:`Show Message` in the
:guilabel:`On Success` field.

.. _website/building_blocks/fields:

Fields
~~~~~~

To add a new field to the form, navigate to the :guilabel:`Style` tab and click the
:guilabel:`+ Field` button next to the :guilabel:`Form` or :guilabel:`Field` section. To modify any
field on the form, select the field, then use the options available in the :guilabel:`Field`
section of the :guilabel:`Style` tab. For example, you can:

- Change the field :guilabel:`Type`.

  .. tip::
     It is also possible to select an :guilabel:`Existing Field` from the database and use the data
     it contains. The fields available depend on the selected action. Property fields added to the
     database can also be used.

  .. spoiler:: Click here to preview all field types.

     .. image:: building_blocks/all-types-of-field.png
        :alt: All types of form fields

     Some fields are visually similar, but the data entered must follow a specific format.

- Edit the field's :guilabel:`Label` and adapt its :guilabel:`Position`.
- Enable a field :guilabel:`Description`. Toggle the switch on and click the default description on
  the form to modify it.
- Add a :guilabel:`Placeholder` or :guilabel:`Default value`.
- Specify if the field is :guilabel:`Required`.
- Edit the field's :doc:`visibility <visibility>` settings.
- Add an :ref:`animation <website/elements/animations>`.

Once you have made the desired changes, click :guilabel:`Save`.

Prefill form fields with URL parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Form fields can be automatically filled using URL query parameters. This is useful for marketing
campaigns, personalized links, or any scenario where you want to pre-populate a form for the
visitor.

.. _website/building_blocks/form/shareable:

Enable shareable links
**********************

URL prefill is **disabled by default** and must be enabled per form with the :guilabel:`Share &
Pre-fill` option. Forms without it ignore query parameters entirely. Once enabled, the shareable
link carries a reserved ``usp_pp`` parameter whose value targets that specific form, so prefill
applies only to it (useful when a page has multiple forms). A link without a ``usp_pp`` parameter
prefills every sharing-enabled form on the page. To enable prefill and get the shareable link for a
form:

#. Open the website editor and click the form block.
#. In the :guilabel:`Style` tab, under the :guilabel:`Form` section, enable the
   :guilabel:`Share & Pre-fill` toggle.
#. A :guilabel:`Shareable Link` field appears with the page URL and the form's ``usp_pp`` token
   (e.g., ``https://example.com/contactus?usp_pp=form-abc123``).
#. Click the :icon:`fa-clipboard` (:guilabel:`Copy Link`) button to copy the link to your
   clipboard.
#. Click :guilabel:`Save`. The link only works once the page is saved with sharing enabled.

.. _website/building_blocks/form/field-name:

Identify field names
********************

Each form field has a **Field Name** used as the query parameter key in the URL. To find it:

#. Open the website editor and click a field in the form.
#. In the :guilabel:`Style` tab, under the :guilabel:`Field` section, locate the
   :guilabel:`Field Name` value.
#. Use this exact name as the query parameter key when constructing the URL.

.. _website/building_blocks/form/construct-url:

Construct the prefill URL
*************************

Append field parameters to the shareable link using the format ``&field_name=value`` (the link
already starts with ``?usp_pp=...``). Separate multiple fields with ``&``.

.. example::
   For a contact form with the shareable link
   ``https://example.com/contactus?usp_pp=form-abc123``, prefill the :guilabel:`Name` and
   :guilabel:`Email` fields:

   .. code-block:: text

      https://example.com/contactus?usp_pp=form-abc123&name=John+Doe&email_from=john@example.com

   When a visitor opens this URL, the form fields are automatically populated with the provided
   values.

For :guilabel:`Selection`, :guilabel:`Radio`, and :guilabel:`Checkbox` fields, the parameter value
must match one of the available option values exactly. For a single checkbox, ``true``, ``1``, and
``on`` check the box, while ``false``, ``0``, and ``off`` uncheck it, even when it is checked by
default.

For :guilabel:`Date` and :guilabel:`Datetime` fields, use the `ISO 8601
<https://en.wikipedia.org/wiki/ISO_8601>`_ format, e.g., ``2026-10-22`` or ``2026-10-22T18:00``. The
date and time must be separated by a ``T``; a space is **not** accepted, so ``2026-10-22 18:00`` (or
``2026-10-22%2018:00``) is ignored even though spaces are otherwise valid in values. The value is
displayed to each visitor in their own local date and time format.

For :guilabel:`Datetime` fields, a time zone in the value is interpreted as the instant it
represents and then shown in each visitor's own time zone: ``2026-10-22T18:00Z`` (UTC) appears as
``20:00`` to a visitor in UTC+2. Use ``Z`` for UTC, or encode a numeric offset's ``+`` as ``%2B``
(e.g., ``2026-10-22T18:00%2B02:00``), since a raw ``+`` in a URL is read as a space.

Incomplete date or time values are accepted, and the missing parts are completed automatically:

- ``2026`` fills January 1, 2026.
- ``2026-10`` fills October 1, 2026.
- ``18:00`` fills today at 18:00.

In all cases, invalid or unmatched values are ignored and the fields keep their default values. The
exception is a :guilabel:`Selection` or :guilabel:`Radio` field with :guilabel:`Add Other` enabled:
an unmatched value selects the :guilabel:`Other` option and fills its input with that value.

For **multiple-checkbox fields**, repeat the field name in the query string for each value:

.. code-block:: text

   https://example.com/contactus?usp_pp=form-abc123&interests=sports&interests=tech

.. note::
   - Values provided by the backend always take precedence over URL parameters. This includes
     server-side ``data-for`` values (e.g., on the Contact Us form) and the ``data-fill-with``
     attribute that prefills name, phone, and email from the logged-in user's contact record.
   - URL parameters are ignored for fields hidden from the visitor — a field whose
     :guilabel:`Visibility` is set to :guilabel:`Hidden`, and internal hidden fields such as
     ``email_to``. Only fields the visitor can see are prefilled, so a shared link cannot silently
     change a value they would not notice.
   - Spaces in values can be encoded as ``+`` or ``%20``.

.. warning::
   On a **sharing-enabled** form, avoid naming visible fields after keys that commonly appear in
   URLs, such as ``usp_pp`` (reserved by this feature), tracking keys (``utm_source``,
   ``utm_medium``, etc.), or routing and search keys (``debug``, ``lang``, ``redirect``, ``page``,
   ``search``, etc.). These keys are frequently appended by analytics tools, ad networks, or Odoo
   itself, and a visible field bearing the same name would be silently prefilled. Hidden fields are
   unaffected — URL parameters never reach them (see the note above).

.. _website/building_blocks/form/no-prefill:

Disable prefill on specific fields
**********************************

To prevent a specific field from being prefilled by URL parameters while still allowing prefill on
other fields in the same form, add the ``data-no-prefill="true"`` attribute to the field's wrapper
element (the ``<div class="s_website_form_field">`` that contains the label and input).

.. example::
   In the page's HTML editor:

   .. code-block:: html

      <div class="s_website_form_field" data-no-prefill="true">
          <label class="s_website_form_label">Verification code</label>
          <input class="s_website_form_input" type="text" name="code"/>
      </div>

   Visitors opening ``?usp_pp=form-abc123&code=ABCD`` will not see ``ABCD`` injected into this
   field, even though other fields on the form continue to prefill normally.

.. note::
   - Backend ``data-for`` values and the ``data-fill-with`` attribute continue to apply to the
     field regardless of ``data-no-prefill``; only URL parameter prefill is blocked.
   - Editing this attribute currently requires the page HTML editor (:menuselection:`Site -->
     HTML/CSS editor`).

Add an Odoo contact form on a non-Odoo website
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can display an Odoo contact form on another website using an iframe. To do so, follow these
steps:

#. **Prepare the Odoo form:** Create a contact form on a page in Odoo Website and remove the
   :ref:`header and footer <website/header_footer/design>`. Make sure only the contact form
   remains on the page.
#. **Generate an embeddable code:** Copy the URL of the Odoo form page and paste it into an iframe
   generator, such as `La Digitale.dev <https://ladigitale.dev/digitools/generateur-iframe>`_ or
   `iFrame Generator <https://www.iframe-generator.com/>`_ . Adjust the width and height for proper
   display.
#. **Add the embedded code to the non-Odoo website:** Open the relevant page’s HTML (in the code
   editor or CMS) and insert the embedded code where the form should be displayed.

.. example::
   Example of an embedded code:

   .. code-block:: html

       <iframe src="https://example.com/odoo-form"
               style="border:0;"
               name="odooForm"
               scrolling="no"
               frameborder="0"
               marginheight="0"
               marginwidth="0"
               height="400px"
               width="600px"
               allowfullscreen>
        </iframe>

.. _website/building_blocks/embed_code:

Embed code
----------

Embedding code allows you to integrate content from third-party services, such as YouTube videos,
Google Maps, and Instagram posts.

After dragging and dropping the :guilabel:`Embed Code` block from the :guilabel:`Inner Content`
section onto a page, click the block, then go to the :guilabel:`Style` tab. Scroll down to the
:guilabel:`Embed Code` section, and, next to :guilabel:`Code`, click :guilabel:`Edit`. Replace the
placeholder code with the custom embed code.

.. image:: building_blocks/embed-code-pop-up.png
   :alt: Add the link to the embedded code you want to point to.
   :scale: 60%

.. warning::
   Only use embed code from sources you trust. Copying and pasting code you do not understand could
   put your data at risk.

.. _website/building_blocks/move_duplicate_delete:

Move, duplicate, or delete a building block
===========================================

To adjust the position and size of a building block, use the following options:

- Drag the turquoise borders on the block to increase or decrease the space at the top or bottom.
- Click the :icon:`fa-chevron-up` (:guilabel:`Move up`) or :icon:`fa-chevron-down` (:guilabel:`Move
  down`) icons to change the block's order.
- Click the :icon:`fa-arrows` (:guilabel:`Drag and move`) icon to move the block on the page.
- When a block contains multiple :ref:`columns <website/building_blocks/columns>`, move a column to
  the left or right by clicking :icon:`fa-chevron-left` (:guilabel:`Move left`) or
  :icon:`fa-chevron-right` (:guilabel:`Move right`).
- Click :icon:`fa-clone` (:guilabel:`Duplicate`) to create a copy of the block. The duplicate is
  added below the original.
- Click :icon:`fa-trash` (:guilabel:`Remove`) to delete the block.

  .. image:: building_blocks/padding-building-block.png
     :alt: Building block options to move, duplicate , or remove it.

.. tip::
   Alternatively, click the block, go to the :guilabel:`Style` tab, and click the :icon:`fa-clone`
   (:guilabel:`Duplicate this block`) or :icon:`fa-trash` (:guilabel:`Remove this block`) icon at
   the top of the tab.

.. example::
   To resize a block, click and drag the dots around its edges to adjust it as needed.

   .. image:: building_blocks/adapt-block-size.png
      :alt: Adapt block size
      :scale: 80%

.. _website/building_blocks/edit:

Edit a building block
=====================

To customize a building block, click it and go to the :guilabel:`Style` tab. Available
customization options vary depending on the type of block selected. Most blocks provide options to
customize the :ref:`background <website/building_blocks/background>`, :ref:`layout
<website/building_blocks/layout>`, :ref:`shape <website/building_blocks/shape>`, and :ref:`content
dimensions <website/building_blocks/content-layout>`.

.. seealso::
   - :doc:`Web design elements <elements>`
   - :doc:`Visibility <visibility>`
   - :doc:`General theme <themes>`

.. _website/building_blocks/background:

Background
----------

To customize the background of a building block, click the color dot or another
:guilabel:`Background` option. Depending on the selected option, you can change the background
:ref:`color <website/themes/theme-colors>` and/or add an :ref:`image <website/elements/images>`,
:ref:`video <website/elements/videos>`, and/or shape. After selecting an option, additional options
are available to customize it.

.. tip::
   In the :ref:`Grid <website/building_blocks/grid>` layout, use the :guilabel:`Send to back` or
   :guilabel:`Bring to front` icons to position elements, such as images and text, behind or in
   front of other elements.

   .. image:: building_blocks/change-block-position.png
      :alt: Move a building block to the back or front.

.. _website/building_blocks/layout:

Layout
------

Most building blocks support two layout styles: :ref:`grid <website/building_blocks/grid>` and
:ref:`column <website/building_blocks/columns>`. To change the default layout, click the block, go
to the :guilabel:`Style` tab, and set the :guilabel:`Layout` field to :guilabel:`Grid` or
:guilabel:`Column`.

.. _website/building_blocks/grid:

Grid
~~~~

The :guilabel:`Grid` layout allows you to reposition and resize elements by dragging and dropping
them. You can also adjust their position and size using the :guilabel:`Spacing` options.

.. _website/building_blocks/columns:

Column
~~~~~~

The :guilabel:`Column` layout allows you to specify the number of elements per line in the block.
To do so, select the block to modify, click the dropdown next to the :guilabel:`Column` field, and
adjust the number. You can then modify a specific column's settings using the options in the
:guilabel:`Column` section of the :guilabel:`Style` tab.

.. note::
   By default, :doc:`on mobile devices <visibility>`, only one element (column) is visible per line
   to ensure that content remains easy to read and accessible on smaller screens. To adjust this
   value, click the :icon:`fa-mobile` (:guilabel:`Mobile Preview`) at the top of the website
   editor and adapt the number of columns. Shapes are hidden by default on mobile devices.

.. _website/building_blocks/shape:

Shape
-----

To add a shape to a building block, click :guilabel:`None` next to the :guilabel:`Shape` setting,
then select a shape. You can change the :ref:`color <website/themes/theme-colors>` and
:guilabel:`Transform` the shape by using the :icon:`fa-arrows-h` (:guilabel:`Horizontal flip`) and
:icon:`fa-arrows-v` (:guilabel:`Vertical flip`) buttons.

Click :icon:`fa-times` :guilabel:`Remove the shape` to remove it and :ref:`manage its visibility on
mobile devices <website/visibility/mobile-and-computer>`.

.. _website/building_blocks/content-layout:

Content dimensions
------------------

To adjust the content dimensions of a building block:

- Use the :guilabel:`Content Width` options to make the content fill the entire width of the page or
  add spacing around it.
- Set the :guilabel:`Auto` :guilabel:`Height` to :guilabel:`50%` or :guilabel:`100%`.

.. _website/building_blocks/custom:

Save a custom building block
============================

Save a customized building block to reuse on other pages. To do so, select it, navigate to
the :guilabel:`Style` tab, and click the :icon:`fa-floppy-o` (:guilabel:`Save this block to use it
elsewhere`) icon. Click the :guilabel:`Save` button in the pop-up window to confirm.

To add a saved building block to the page, navigate to the :icon:`fa-plus` :guilabel:`Blocks` tab
and drag and drop the :guilabel:`Custom` categorical block. In the pop-up window that opens, click
the desired block in the :guilabel:`Custom` category.

.. tip::
   In the :guilabel:`Insert a block` pop-up window, click :icon:`fa-pencil` (:guilabel:`Rename`) to
   rename the custom block or :icon:`fa-trash` (:guilabel:`Remove`) to delete it.

.. _website/building_blocks/anchor:

Create an anchor link
=====================

Anchor links are hyperlinks that direct users to a specific section of a page. To create an anchor
link for a block, follow these steps:

#. Click :guilabel:`Edit` and select the block you want to link to.
#. At the top of the :guilabel:`Style` tab, click :icon:`fa-link` (:guilabel:`Create and copy a link
   targeting this block or edit it`).
#. To edit the default anchor name, click :guilabel:`Edit` in the green pop-up message that opens in
   the upper-right corner.
#. Replace the anchor name and click :guilabel:`Save & Copy`.

Once the anchor is saved, you can :ref:`link to it <website/elements/links>` from anywhere on your
website.

.. toctree::
   :titlesonly:

   building_blocks/forms
