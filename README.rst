This library is deprecated, please use rollbar-agent_
=====================================================

ratchet-agent
=============
A daemon to monitor log files and push messages to Ratchet.io_.


Requirements
------------
ratchet-agent requires:

- A unix-like system (tested on Fedora Linux and Mac OS X)
- Python 2.6+
- requests 0.13.1+
- a Ratchet.io_ account


Installation
------------
Install with pip::

    pip install ratchet-agent

This will install the ratchet-agent files in the root directory of your virtualenv. Or if you'd prefer, clone this git repo:

    git clone https://github.com/ratchetio/ratchet-agent.git

See Configuration for configuration options and setup.

ratchet-agent comes with an example init.d script, chkconfig compatible and tested on Fedora Linux. To install it, symlink ``ratchet-agent-init.sh`` to ``/etc/init.d/ratchet-agent`` and add to chkconfig::

    ln -s /path/to/ratchet-agent/ratchet-agent-init.sh /etc/init.d/ratchet-agent
    chkconfig --add ratchet-agent
    chkconfig on ratchet-agent
    service ratchet-agent start

Configuration
-------------
Configuration options for ratchet-agent itself are in `ratchet-agent.conf`. If you're using the init script, it has a few of its own configuration variables inside which control how it runs.

**ratchet-agent.conf**
At the bare minimum, you will want to change the following variables:

- ``params.access_token`` -- your Ratchet.io access token
- ``targets`` -- white-space-separated list of files or directories (non-recursive) to process.

Setting the following variables will improve github integration:

- ``params.root`` -- path to your code root
- ``params.branch`` -- the current branch

Other options are documented in the sample config file.

**ratchet-agent-init.sh**
Configuration variables should be self-explanatory. If you're not using a virtualenv, set ``VIRTUALENV=""``.


Contributing
------------

Contributions are welcome. The project is hosted on github at http://github.com/ratchetio/ratchet-agent


Additional Help
---------------
If you have any questions, feedback, etc., drop me a line at brian@ratchet.io


.. _rollbar-agent: https://github.com/rollbar/rollbar-agent
.. _Ratchet.io: http://ratchet.io/
.. _`download the zip`: https://github.com/ratchetio/django_ratchet/zipball/master
.. _ratchet-agent: http://github.com/ratchetio/ratchet-agent
