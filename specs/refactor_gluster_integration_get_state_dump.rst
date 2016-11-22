================================================
Refactor Gluster Integration's state dump module
================================================

The gluster get-state output is consumed by tendrl-gluster-integration, we
need to refactor the way Tendrl consumes and processes the get-state output

Notes:

* In light of new changes to gluster get-state
  http://review.gluster.org/#/c/15889

Problem description
===================

Current Tendrl way of consuming and processing is not robust enough to adopt
with the Tendrl object namespacing, We also need to accomodate lates
changes to the gluster get-state output.

Use Cases
=========

This addresses the use case of obtaining refereshed gluster cluster state

Proposed change
===============

* General re-factoring of code handling gluster get-state

* Accomodate latest changes to output of gluster get-state w.r.t volume options

Alternatives
------------

None

Data model impact
-----------------

* All Persistor models will be affected , especially Volume


REST API impact
---------------

* Tendrl object definitions for Volume will need to be updated for
  accomodating the newly added Volume options gluster get-state dump

Security impact
---------------

None

Notifications/Monitoring impact
-------------------------------

* Monitoring might want to take note of the new volume options

Other end user impact
---------------------

None

Performance Impact
------------------

None

Other deployer impact
---------------------

None

Developer impact
----------------

None

Implementation
==============

* Add_github_issues_link_here


Assignee(s)
-----------

Primary assignee:
  shtripat


Other contributors:
  r0h4n

Work Items
----------

TODO (shtripat)

Dependencies
============

* Required Gluster 3.9 + patch http://review.gluster.org/#/c/15889

Testing
=======

TODO (shtripat)


Documentation Impact
====================

TODO (shtripat)

References
==========

* https://www.redhat.com/archives/tendrl-devel/2016-November/msg00063.html
