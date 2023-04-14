argus_notification_{{ cookiecutter.notification_system }}
==================={% for _ in cookiecutter.notification_system %}={% endfor %}

This is a plugin to send notifications to {{ cookiecutter.notification_system }} from
`Argus <https://github.com/Uninett/argus-server>`_

Django settings
---------------

Add ``argus_notification_{{ cookiecutter.notification_system }}.MSTeamsNotification`` to ``MEDIA_PLUGINS``::

    MEDIA_PLUGINS = [
        ..
        "argus_notification_{{ cookiecutter.notification_system }}.MSTeamsNotification",
    ]

Configuration
-------------

DESCRIBE WHAT GOES IN THE SETTINGS-FIELD

You can test without invoking the frontend by adding the webhook manually in
Django admin.

POST-ing to the API:

/api/v2/notificationprofiles/destinations/, POSTed body::

    {
      "media": "{{ cookiecutter.notification_system }}",
      "label": "whatever",
      "settings": {
        UPDATE THIS
      }
    }

GET-ing from the API:

/api/v2/notificationprofiles/destinations/{id}/, received result::

  {
    "pk": 0,
    "media": {
      "slug": "{{ cookiecutter.notification_system }}",
      "name": "UPDATE THIS"
    },
    "label": "whatever",
    "suggested_label": "whatever",
    "settings": {
      UPDATE THIS
    }
  }
