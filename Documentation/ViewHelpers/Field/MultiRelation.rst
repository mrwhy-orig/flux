.. include:: /Includes.rst.txt

.. _fluidtypo3-flux-field-multirelation:

===================
field.multiRelation
===================


Select one or more database records from several tables.

In comparison to ``RelationViewHelper``, only the list with selected
items is visible on the left.
The right side contains a "browse" button that opens a popup.

Related: ``RelationViewHelper``.

Example: Select from multiple tables
====================================

Select pages and content elements:

    <flux:field.multiRelation name="settings.records"
                              table="pages,tt_content"
                              maxItems="5" />

Example: Content element selector with autocomplete
===================================================

Add a wizard to search for content elements, instead of opening a popup:

    <flux:field.multiRelation name="settings.elements"
                              table="tt_content"
                              maxItems="5">
        <flux:wizard.suggest />
    </flux:field.multiRelation>

DEPRECATED - use flux:field instead

Arguments
=========


.. _field.multirelation_name:

name
----

:aspect:`DataType`
   string

:aspect:`Required`
   true
:aspect:`Description`
   Name of the attribute, FlexForm XML-valid tag name string

.. _field.multirelation_label:

label
-----

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Label for the attribute, can be LLL: value. Optional - if not specified, Flux tries to detect an LLL label named "flux.fluxFormId.fields.foobar" based on field name, in scope of extension rendering the Flux form. If field is in an object, use "flux.fluxFormId.objects.objectname.foobar" where "foobar" is the name of the field.

.. _field.multirelation_default:

default
-------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Default value for this attribute

.. _field.multirelation_required:

required
--------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, this attribute must be filled when editing the FCE

.. _field.multirelation_exclude:

exclude
-------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, this field becomes an "exclude field" (see TYPO3 documentation about this)

.. _field.multirelation_transform:

transform
---------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Set this to transform your value to this type - integer, array (for csv values), float, DateTime, Vendor\MyExt\Domain\Model\Object or ObjectStorage with type hint.

.. _field.multirelation_enabled:

enabled
-------

:aspect:`DataType`
   boolean

:aspect:`Default`
   true

:aspect:`Required`
   false
:aspect:`Description`
   If FALSE, disables the field in the FlexForm

.. _field.multirelation_requestupdate:

requestUpdate
-------------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, the form is force-saved and reloaded when field value changes

.. _field.multirelation_displaycond:

displayCond
-----------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Optional "Display Condition" (TCA style) for this particular field. See: https://docs.typo3.org/typo3cms/TCAReference/Reference/Columns/Index.html#displaycond

.. _field.multirelation_inherit:

inherit
-------

:aspect:`DataType`
   boolean

:aspect:`Default`
   true

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, the value for this particular field is inherited - if inheritance is enabled by the ConfigurationProvider

.. _field.multirelation_inheritempty:

inheritEmpty
------------

:aspect:`DataType`
   boolean

:aspect:`Default`
   true

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, allows empty values (specifically excluding the number zero!) to be inherited - if inheritance is enabled by the ConfigurationProvider

.. _field.multirelation_clear:

clear
-----

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, a "clear value" checkbox is displayed next to the field which when checked, completely destroys the current field value all the way down to the stored XML value

.. _field.multirelation_variables:

variables
---------

:aspect:`DataType`
   mixed

:aspect:`Default`
   array ()

:aspect:`Required`
   false
:aspect:`Description`
   Freestyle variables which become assigned to the resulting Component - can then be read from that Component outside this Fluid template and in other templates using the Form object from this template

.. _field.multirelation_extensionname:

extensionName
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   If provided, enables overriding the extension context for this and all child nodes. The extension name is otherwise automatically detected from rendering context.

.. _field.multirelation_config:

config
------

:aspect:`DataType`
   mixed

:aspect:`Default`
   array ()

:aspect:`Required`
   false
:aspect:`Description`
   Raw TCA options - passed directly to "config" section of created field and overrides anything generated by the component itself. Can be used to provide options that Flux itself does not support, and can be used to pass root-level arguments for a "userFunc"

.. _field.multirelation_validate:

validate
--------

:aspect:`DataType`
   string

:aspect:`Default`
   'trim'

:aspect:`Required`
   false
:aspect:`Description`
   FlexForm-type validation configuration for this input

.. _field.multirelation_size:

size
----

:aspect:`DataType`
   integer

:aspect:`Default`
   1

:aspect:`Required`
   false
:aspect:`Description`
   Size of the selector box

.. _field.multirelation_multiple:

multiple
--------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, allows selecting the same value multiple times

.. _field.multirelation_minitems:

minItems
--------

:aspect:`DataType`
   integer

:aspect:`Required`
   false
:aspect:`Description`
   Minimum required number of items to be selected

.. _field.multirelation_maxitems:

maxItems
--------

:aspect:`DataType`
   integer

:aspect:`Default`
   1

:aspect:`Required`
   false
:aspect:`Description`
   Maxium allowed number of items to be selected

.. _field.multirelation_itemliststyle:

itemListStyle
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Overrides the default list style when maxItems > 1

.. _field.multirelation_selectedliststyle:

selectedListStyle
-----------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Overrides the default selected list style when maxItems > 1 and renderType is SelectSingle

.. _field.multirelation_items:

items
-----

:aspect:`DataType`
   mixed

:aspect:`Required`
   false
:aspect:`Description`
   Items for the selector; array / CSV / Traversable / Query supported

.. _field.multirelation_emptyoption:

emptyOption
-----------

:aspect:`DataType`
   mixed

:aspect:`Required`
   false
:aspect:`Description`
   If not-FALSE, adds one empty option/value pair to the generated selector box and tries to use this property's value (cast to string) as label.

.. _field.multirelation_translatecsvitems:

translateCsvItems
-----------------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, attempts to resolve a LLL label for each value provided as CSV in "items" attribute using convention for lookup "$field.option.123" if given "123" as CSV item value. Field name is determined by normal Flux field name conventions

.. _field.multirelation_itemsprocfunc:

itemsProcFunc
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Function for serving items. See TCA "select" field "itemsProcFunc" attribute

.. _field.multirelation_table:

table
-----

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Define foreign table name to turn selector into a record selector for that table

.. _field.multirelation_condition:

condition
---------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Condition to use when selecting from "foreignTable", supports FlexForm `foreign_table_where` markers

.. _field.multirelation_mm:

mm
--

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Optional name of MM table to use for record selection

.. _field.multirelation_foreignfield:

foreignField
------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   The `foreign_field` is the field of the child record pointing to the parent record. This defines where to store the uid of the parent record.

.. _field.multirelation_foreignlabel:

foreignLabel
------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   If set, it overrides the label set in `TCA[foreign_table]['ctrl']['label']` for the inline-view.

.. _field.multirelation_foreignselector:

foreignSelector
---------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   A selector is used to show all possible child records that could be used to create a relation with the parent record. It will be rendered as a multi-select-box. On clicking on an item inside the selector a new relation is created. The `foreign_selector` points to a field of the `foreign_table` that is responsible for providing a selector-box - this field on the `foreign_table` usually has the type "select" and also has a `foreign_table` defined.

.. _field.multirelation_foreignsortby:

foreignSortby
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Field on the child record (or on the intermediate table) that stores the manual sorting information.

.. _field.multirelation_foreigndefaultsortby:

foreignDefaultSortby
--------------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   If a fieldname for `foreign_sortby` is defined, then this is ignored. Otherwise this is used as the "ORDER BY" statement to sort the records in the table when listed.

.. _field.multirelation_foreigntablefield:

foreignTableField
-----------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   The field of the child record pointing to the parent record. This defines where to store the table name of the parent record. On setting this configuration key together with `foreign_field`, the child record knows what its parent record is - so the child record could also be used on other parent tables.

.. _field.multirelation_foreignunique:

foreignUnique
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Field which must be uniue for all children of a parent record.

.. _field.multirelation_symmetricfield:

symmetricField
--------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   In case of bidirectional symmetric relations, this defines in which field on the foreign table the uid of the "other" parent is stored.

.. _field.multirelation_symmetriclabel:

symmetricLabel
--------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   If set, this overrides the default label of the selected `symmetric_field`.

.. _field.multirelation_symmetricsortby:

symmetricSortby
---------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Works like `foreign_sortby`, but defines the field on `foreign_table` where the "other" sort order is stored.

.. _field.multirelation_localizationmode:

localizationMode
----------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Set whether children can be localizable ('select') or just inherit from default language ('keep').

.. _field.multirelation_localizechildrenatparentlocalization:

localizeChildrenAtParentLocalization
------------------------------------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   Defines whether children should be localized when the localization of the parent gets created.

.. _field.multirelation_disablemovingchildrenwithparent:

disableMovingChildrenWithParent
-------------------------------

:aspect:`DataType`
   boolean

:aspect:`Required`
   false
:aspect:`Description`
   Disables that child records get moved along with their parent records.

.. _field.multirelation_showthumbs:

showThumbs
----------

:aspect:`DataType`
   boolean

:aspect:`Default`
   true

:aspect:`Required`
   false
:aspect:`Description`
   If TRUE, adds thumbnail display when editing in BE

.. _field.multirelation_matchfields:

matchFields
-----------

:aspect:`DataType`
   mixed

:aspect:`Default`
   array ()

:aspect:`Required`
   false
:aspect:`Description`
   When using manyToMany you can provide an additional array of field=>value pairs that must match in the relation table

.. _field.multirelation_oppositefield:

oppositeField
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Name of the opposite field related to a proper mm relation
