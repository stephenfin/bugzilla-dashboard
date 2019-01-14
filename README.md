Bugzilla Dashboard
==================

**WIP!**

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

To Do
-----

- Show loading dialog when results are loading
- Display warnings if no results found (usually a typo)
- Make filters applied via the filter dialog persistent
- Stop defaulting to my username and ask users what they want
- Add additional products besides `openstack-nova`
