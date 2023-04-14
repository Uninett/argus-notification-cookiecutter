How to use this cookiecutter
============================

If you do not have cookiecutter you will have to install it.

Then, run::

    cookiecutter argus_notification_cookiecutter

It will ask you for two things:

1. A snake case name for your notification system
2. Your dependencies. If more than one, separate them with a comma

For example:

If you answered "discord" for ``notification_system`` a directory is created
that is called ``argus_notification_discord``.

Here's the generated directory tree inside ``argus_notification_discord``::

    ├── LICENSE
    ├── Makefile
    ├── pyproject.toml
    ├── README.rst
    ├── runtests.py
    ├── src
    │   └── argus_notification_discord.py
    ├── tests
    │   ├── __init__.py
    │   ├── test_argus_notification_discord.py
    │   └── test_settings.py
    └── tox.ini

Write your plugin in the file ``src/argus_notification_discord.py``, your tests
in ``tests/test_argus_notification_discord.py`` and most importantly your docs
in ``README.rst``.

Your README must explain any extra django settings needed besides appending to
``MEDIA_PLUGINS``, for instance any settings common for all destinations. The
generated README has a minimal skeleton, upper case text must be replaced.

Tests can be run with ``tox`` or directly via ``runtests.py``.
