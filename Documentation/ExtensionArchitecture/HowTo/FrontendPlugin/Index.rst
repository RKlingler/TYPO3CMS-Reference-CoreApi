.. include:: /Includes.rst.txt
.. index::
   pair: Extension development; Frontend plugin

.. _frontend_plugin:

===============
Frontend plugin
===============

The term "frontend plugin" describes a part of a TYPO3 extension that is
handled like a content element (can be inserted like a record/element in
the TYPO3 backend by editors), which will deliver dynamic output when
rendered in the frontend. The distinction and boundaries to regular content
are sometimes not easy to draw, because also "regular" content elements
are often able to perform dynamic output (for example with TypoScript
configuration, Fluid data processors or ViewHelpers).

For a long time, TYPO3 provided a "General Plugin" to be selected as a
content element (setting the content record :sql:`CType` to :sql:`'list'`), and then the sub-type
would indicate which kind of frontend plugin to be used
(setting the content record :sql:`list_type`). It is recommended to only
use the :sql:`CType` based registration.

There are different technology choices to create frontend plugins in TYPO3.

For pure output it is often sufficient to use a
:ref:`FLUIDTEMPLATE <t3tsref:cobj-fluidtemplate>` in combination with
:ref:`DataProcessors <t3tsref:dataProcessing>`. See also
:ref:`Creating a custom content element <adding-your-own-content-elements>`.

For scenarios with user input and or complicated data operations consider
using :ref:`Extbase <extbase>` (specifically
:ref:`Registration of frontend plugins <t3coreapi:extbase_registration_of_frontend_plugins>`).

It is also possible to create a frontend plugin using Core functionality
only.

..  todo: Document how to create a frontend plugin without Extbase.
