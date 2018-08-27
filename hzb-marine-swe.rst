Use case alignment HZB - Marine SWE group
=========================================

This document considers two use cases for persistent identification of
instruments: the `Use case description at HZB`_ and the `Use case
description “marine SWE group”`_.  The metadata properties that both
use cases suggest are listed and aligned in the table below.

The first two columns are the property name suggested in the HZB and
the marine SWE use case respectively.  The third column lists the
suggested occurence.  The fourth column provides a definition.  If
essentially the same property is suggested in both use cases, the
table has one common row for both.  In this case, the third column may
contain two values separated by a slash if the use cases do not
agree.  The definition in the fourth column tries to formulate a
compromise between both definitions.

Note that the HZB use case defines some properties as sub properties
of other properties.  This is not the case for the Marine SWE use case.

+-----------------------+--------------+-----------+---------------------------+----------------------+
| Property HZB          | Property SWE | Occurence | Definition                | Type                 |
+=======================+==============+===========+===========================+======================+
| Identifier            | Identifier   | 1         | A unique string that      | PID                  |
|                       |              |           | identifies the instrument |                      |
|                       |              |           | instance                  |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
|                       | Inventory    | 0..1      | The identifier registered | String or PID        |
|                       | Number       |           | in the owner              |                      |
|                       |              |           | institution's device or   |                      |
|                       |              |           | asset catalogs or         |                      |
|                       |              |           | management systems        |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| Name                  | Local Name   | 1..n /    | The name identifying the  | Text                 |
|                       |              | 0..1      | instrument, may be mainly |                      |
|                       |              |           | used locally within the   |                      |
|                       |              |           | owning institution        |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| URL                   |              | 1         | URL of a landing page     | URL                  |
|                       |              |           | providing more            |                      |
|                       |              |           | information               |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| Owner                 |              | 1         | Organization or entity    | Text                 |
|                       |              |           | that operates the         |                      |
|                       |              |           | instrument                |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| ownerIdentifier       |              | 0..1      | Persistent identifier of  | PID                  |
|                       |              |           | the Owner, such as an     |                      |
|                       |              |           | ISNI                      |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| Manufacturer          | Manufacturer | 0..1      | Name of the manufacturer  | Text (or PID)        |
|                       |              |           | that created the          |                      |
|                       |              |           | instrument                |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
|                       | Manufacturer | 0..1      | The number/id given to    |                      |
|                       | Identifier   |           | the product by the        |                      |
|                       |              |           | manufacturer, Aka         |                      |
|                       |              |           | manufacturer part number  |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| modelName             | Model Name   | 0..1 / 1  | Name of the type of the   | Text                 |
|                       |              |           | device given by the       |                      |
|                       |              |           | instrument's manufacturer |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| deviceURL             |              | 0..1      | URL providing information | URL                  |
|                       |              |           | on the type of the        |                      |
|                       |              |           | device, such as technical |                      |
|                       |              |           | specifications            |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
|                       | Serial       | 1         | Serial number issued to   | Text                 |
|                       | Number       |           | the instrument instance   |                      |
|                       |              |           | by the manufacturer       |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| Description           |              | 0..1      | Text describing the       | Free Text            |
|                       |              |           | instrument                |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
|                       | Instrument   | 0..n      | A category for the        | PID                  |
|                       | Category     |           | instrument such as 'CTD'. |                      |
|                       |              |           | Preferred PID is from the |                      |
|                       |              |           | SDN vocabulary for        |                      |
|                       |              |           | instruments               |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
|                       | Observable   | 0..n      | Aka: Measurable Property  | Text                 |
|                       | Property     |           |                           |                      |
|                       |              |           |                           |                      |
|                       |              |           |                           |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| Date                  |              | 0..n      | Dates relevant for this   | ISO 8601             |
|                       |              |           | instrument, maybe a       |                      |
|                       |              |           | single date or an         |                      |
|                       |              |           | interval                  |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| dateType              |              | 1         | Mandatory sub property    | Controlled list      |
|                       |              |           | for each Date             | of values:           |
|                       |              |           |                           | InOperation,         |
|                       |              |           |                           | Revised, ...         |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| RelatedIdentifier     |              | 0..1      | Identifier of a related   | PID                  |
|                       |              |           | ressource, PID            |                      |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| relatedIdentifierType |              | 1         | Type of the PID,          | Controlled list      |
|                       |              |           | mandatory sub property    | of values:           |
|                       |              |           | for each                  | Instrument-PID,      |
|                       |              |           | RelatedIdentifier         | DOI, Handle,         |
|                       |              |           |                           | URL, URN,            |
|                       |              |           |                           | ...                  |
+-----------------------+--------------+-----------+---------------------------+----------------------+
| relationType          |              | 1         | Description of the        | controlled list of   |
|                       |              |           | relation, mandatory sub   | values:              |
|                       |              |           | property for each         | IsDescribedBy,       |
|                       |              |           | RelatedIdentifier         | IsNewVersionOf,      |
|                       |              |           |                           | IsPreviousVersionOf, |
|                       |              |           |                           | HasComponent,        |
|                       |              |           |                           | IsComponentOf, ...   |
+-----------------------+--------------+-----------+---------------------------+----------------------+


.. _Use case description at HZB: https://docs.google.com/document/d/1NazXoTUmQZG68ijA9569iRuDl0aDIMegrtnwy-cnaqw
.. _Use case description “marine SWE group”: https://docs.google.com/document/d/1yj_iOABBPmpX38b9khawJjr-yyo96W6GCxxN4LKpQmo
