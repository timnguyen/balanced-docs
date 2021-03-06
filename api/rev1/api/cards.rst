.. _cards:

Cards
=====

A ``Card`` is a funding instrument resource that represents a credit card.
Credit card information is securely vaulted is referenced by a ``href``.
A ``Card`` may be created multiple times, each ``Card`` represented by
a unique href. Each href may only be associated one time and to only
one ``Customer``. Once associated, a ``Card`` may not be disassociated
from the ``Customer``, it may only be unstored.

|

.. container:: header3

  Available Query Filters

.. cssclass:: dl-horizontal dl-params filters

  .. dcode:: query Cards


Create a Card (Direct)
------------------------

Creates a new card.

.. note::
  :header_class: alert alert-tab-red
  :body_class: alert alert-red
  
  This method is not recommended for production environments. Please use balanced.js to
  create cards.

.. cssclass:: dl-horizontal dl-params

   .. dcode:: form cards.create

.. container:: code-white

  .. dcode:: scenario card_create


Fetch a Card
---------------

Fetches the details of a card that has previously been created.
Supply the ``uri`` that was returned from your previous request, and
the corresponding card information will be returned. The same
information is returned when creating the card.

.. container:: method-description

  .. no request

.. container:: code-white

  .. dcode:: scenario card_show


List All Cards
--------------

Returns a list of cards that you've created.

.. cssclass:: dl-horizontal dl-params

  ``limit``
      *optional* integer. Defaults to ``10``.

  ``offset``
      *optional* integer. Defaults to ``0``.

.. container:: code-white

  .. dcode:: scenario card_list


Update a Card
-------------

Update information on a previously created card.

.. note::
  :header_class: alert alert-tab-red
  :body_class: alert alert-red
  
  Once a card has been associated to a customer, it cannot be
  associated to another customer.

.. cssclass:: dl-horizontal dl-params

  .. dcode:: form cards.update

.. container:: code-white

  .. dcode:: scenario card_update


Deleting a Card
---------------------

Permanently delete a card. It cannot be undone. All debits associated
with a deleted credit card will not be affected.

.. container:: method-description

   .. no request

.. container:: code-white

   .. dcode:: scenario card_delete


Charge a Card
------------------

Charge a tokenized credit card.

.. cssclass:: dl-horizontal dl-params

  .. dcode:: form debits.create

.. container:: code-white

  .. dcode:: scenario card_debit
