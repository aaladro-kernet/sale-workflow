===================
Sale Block no Stock
===================

.. 
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! source digest: sha256:5a8f225c0c74ca532066496eb47293120904ad368c72b5ca8e7354439c67d01f
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Alpha-red.png
    :target: https://odoo-community.org/page/development-status
    :alt: Alpha
.. |badge2| image:: https://img.shields.io/badge/licence-LGPL--3-blue.png
    :target: http://www.gnu.org/licenses/lgpl-3.0-standalone.html
    :alt: License: LGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fsale--workflow-lightgray.png?logo=github
    :target: https://github.com/OCA/sale-workflow/tree/16.0/sale_block_no_stock
    :alt: OCA/sale-workflow
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/sale-workflow-16-0/sale-workflow-16-0-sale_block_no_stock
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runboat-Try%20me-875A7B.png
    :target: https://runboat.odoo-community.org/builds?repo=OCA/sale-workflow&target_branch=16.0
    :alt: Try me on Runboat

|badge1| |badge2| |badge3| |badge4| |badge5|

This module extends the functionality of Sales to support blocking sales
and to allow you to ensure you are capable to send product you have in
stock.

When a Sale Order is going to be confirmed, it will be checked if the
quantity demanded exceeds that of the field selected in the
configuration, and in this case a wizard will appear to allow you to fix
quantities indicating what is the maximum quantity that can be ordered.

Then, you can adjust UoM quantities, Packaging quantities or move
remaining unfixed lines to a new order.

If the user who is confirming an order has a group that is allowed, an
extra option to confirm the Order with errors will appear on the Wizard.

This module only can block lines with product type 'product' (storable
products).

.. IMPORTANT::
   This is an alpha version, the data model and design can change at any time without warning.
   Only for development or testing purpose, do not use in production.
   `More details on development status <https://odoo-community.org/page/development-status>`_

**Table of contents**

.. contents::
   :local:

Use Cases / Context
===================

This module was developed because sometimes you don't want to allow a
sale to be confirmed when there is no enough product to sold.

It will be useful for you if selling more than you have in stock or
planned is not a desired behaviour.

Configuration
=============

To configure this module, you need to:

1. Go to Settings > Sales > Quotations & Orders > Blocking sales due to
   lack of stock
2. Fill *Field to compare against the quantity demanded*. Possible
   values:

-  *virtual_available_at_date*: Planned quantity to be in stock on the
   day of delivery
-  *qty_available_today*: Quantity available in stock today
-  *free_qty_today*: Quantity available without reserve in stock

3. Fill *Groups allowed to bypass the block*

Usage
=====

To use this module, you need to:

1. Go to Settings > Sales > Quotations & Orders > Blocking sales due to
   lack of stock
2. Fill *Field to compare against the quantity demanded*: This field
   will be used to check if the quantity demanded is less than or equal
   to the value marked in this field. Set it to
   *virtual_available_at_date* for this test.
3. Fill *Groups allowed to bypass the block*: These groups will allow
   the blocking to be bypassed if the quantity demanded exceeds the
   quantity we want to check. Leave it blank to not allow any group to
   bypass that restriction.
4. Create a Product and set it to be storable.
5. Create a Purchase Order for the product and confirm it. Set the
   Picking Schedule Date on 3 days.
6. Create a Sale Order with the product and set the Commitment Date on 2
   days. Confirm it and check the wizard.
7. Click on *Ajust UoM Quantity* and see the order has been modified to
   match forecasted quantity.

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/sale-workflow/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us to smash it by providing a detailed and welcomed
`feedback <https://github.com/OCA/sale-workflow/issues/new?body=module:%20sale_block_no_stock%0Aversion:%2016.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
-------

* Moduon

Contributors
------------

-  Eduardo de Miguel (`Moduon <https://www.moduon.team/>`__)
-  Rafael Blasco (`Moduon <https://www.moduon.team/>`__)

Other credits
-------------

The development of this module has been financially supported by:

-  Ulzama

Maintainers
-----------

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

.. |maintainer-Shide| image:: https://github.com/Shide.png?size=40px
    :target: https://github.com/Shide
    :alt: Shide

Current `maintainer <https://odoo-community.org/page/maintainer-role>`__:

|maintainer-Shide| 

This module is part of the `OCA/sale-workflow <https://github.com/OCA/sale-workflow/tree/16.0/sale_block_no_stock>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.
