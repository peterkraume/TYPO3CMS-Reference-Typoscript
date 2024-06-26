..  include:: /Includes.rst.txt
..  _splitProcessor:

==============
SplitProcessor
==============

The :php:`SplitProcessor` allows to split values separated with a delimiter
from a single database field. The result is an array that can be iterated over.
Whitespaces are automatically trimmed.

..  _splitProcessor-options:

Options
=======

..  _splitProcessor-if:

if
--

..  confval:: if
    :name: splitProcessor-if
    :Required: false
    :type: :ref:`if` condition
    :Default: ''

    Only if the condition is met the data processor is executed.


..  _splitProcessor-fieldName:

fieldName
---------

..  confval:: fieldName
    :name: splitProcessor-fieldName
    :Required: true
    :type: :ref:`data-type-string` / :ref:`stdWrap`
    :Default: ''

    Name of the field to be used.


..  _splitProcessor-as:

as
--

..  confval:: as
    :name: splitProcessor-as
    :Required: false
    :type: :ref:`data-type-string`
    :Default: defaults to the fieldName

    The variable name to be used in the Fluid template.


..  _splitProcessor-delimiter:

delimiter
---------

..  confval:: delimiter
    :name: splitProcessor-delimiter
    :Required: false
    :type: :ref:`data-type-string` / :ref:`stdWrap`
    :Default: Line Feed
    :Example: ","

    The field delimiter, a character separating the values.


..  _splitProcessor-filterIntegers:

filterIntegers
--------------

..  confval:: filterIntegers
    :name: splitProcessor-filterIntegers
    :Required: false
    :type: :ref:`data-type-boolean` / :ref:`stdWrap`
    :Default: 0
    :Example: 1

    If set to `1`, all values are being cast to int.


..  _splitProcessor-filterUnique:

filterUnique
------------

..  confval:: filterUnique
    :name: splitProcessor-filterUnique
    :Required: false
    :type: :ref:`data-type-boolean` / :ref:`stdWrap`
    :Default: 0
    :Example: 1

    If set to `1`, all duplicates will be removed.


..  _splitProcessor-removeEmptyEntries:

removeEmptyEntries
------------------

..  confval:: removeEmptyEntries
    :name: splitProcessor-removeEmptyEntries
    :Required: false
    :type: :ref:`data-type-boolean` / :ref:`stdWrap`
    :Default: 0
    :Example: 1

    If set to `1`, all empty values will be removed.

..  _splitProcessor-example-split-url:

Example: Splitting a URL
========================

Please see also :ref:`dataProcessing-about-examples`.


TypoScript
----------

With the help of the :php:`SplitProcessor` the following scenario is
possible:

..  include:: /CodeSnippets/DataProcessing/TypoScript/SplitProcessor.rst.txt

..  versionadded:: 12.1
    One can use the alias :typoscript:`split` instead
    of the fully-qualified class name
    :php:`\TYPO3\CMS\Frontend\DataProcessing\SplitProcessor`.

The Fluid template
------------------

In the Fluid template then iterate over the split data:

..  include:: /CodeSnippets/DataProcessing/Template/DataProcSplit.rst.txt


Output
------

The array now contains the split strings:

..  include:: /Images/AutomaticScreenshots/DataProcessing/SplitProcessor.rst.txt
