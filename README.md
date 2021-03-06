Bugzilla Dashboard
==================

A simple dashboard to track my downstream (Red Hat) bugs for OpenStack nova and
related projects. Information retrieved using the [Bugzilla 5 REST
API](https://bugzilla.readthedocs.io/en/latest/api/). If you don't work in my
team, this probably isn't that useful.

Built using:

- [Vue.js](https://vuejs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [FontAwesome](https://fontawesome.com/)

Usage
-----

Only my bugs are show at the moment. You can change this by passing the
`username` keyword:

    ?username=foo

Similarly, bugs against all releases are shown. You can change this by passing
the `release` keyword:

    ?release=15.0 (Stein)

It's also possible to do this via the filter window but those filters are not
currently persisted across refreshes.

Development
-----------

This uses `vue-router`, meaning you need to deploy behind a server. Python's
`SimpleHTTPServer` is more than good enough.

    $ cd bugzilla-tracker
    $ python -m SimpleHTTPServer  # browse to http://localhost:8000

Note, however, that this still won't work due to the hardcoded index URL and
CORS on the REST API. You can resolve the former by:

    $ sed -i 's/\/~sfinucan\/bug-dashboard//' index.html

The latter is still a WIP though and needs to be resolved by the admins of the
[Red Hat instance](https://bugzilla.redhat.com/show_bug.cgi?id=1666031). We
could investigate the use of JSONP but axios [does not support this
natively](https://github.com/axios/axios/blob/master/COOKBOOK.md#jsonp).

Useful resources
----------------

- [Bugzilla REST API documentation](https://bugzilla.readthedocs.io/en/latest/api/core/v1/)
- [Axios Tutorial](https://flaviocopes.com/axios/)
