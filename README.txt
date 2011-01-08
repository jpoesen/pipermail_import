
PIPERMAIL IMPORT
================

Warning: Experimental.

This is the first stab at providing support for Pipermail,
namely importing Pipermail messages from archive files
and creating one node per message. No other Pipermail 
interaction is foreseen at this time.

There are still many things hardcoded. Expect to get your hands dirty.

Requirements
============
- PHP Multibyte String extension needs to be enabled 
  (http://php.net/manual/en/ref.mbstring.php)

Current features
================

- creates content type 'pipermail'
- imports Pipermail archives into said content type, creating a node per message
- imports message content into body field
- imports message headers into corresponding fields
-- headers: From:, Date:, Subject:, In-Reply-To:, References:, Message-ID: 
- import skips messages that already exist (Message-ID must be unique) 

Usage
===== 
- Put a Pipermail archive file in public://
- modify the code to match the filename
- hit /admin/structure/pipermail

Limitations
===========
- import file name and location still hardcoded
- message boundary string still hardcoded
- not tested with any other Pipermail archive files than the ones at hand

Roadmap
=======
- write tests
- use batch api
- provide message hierarchy through node_reference fields
- provide integration with Feeds for import
- provide integration with Views (default message archive views)
- provide drush command extension for import

A note of thanks to
===================
- The excellent 'Pro Drupal 7 Development' book
- DevelopmentSeed's Feeds module (http://drupal.org/project/feeds)
- Ronald Istos (http://www.istos.it/blog/drupal-entities/drupal-entities-part-3-programming-hello-drupal-entity)

License
=======
see LICENSE.txt
