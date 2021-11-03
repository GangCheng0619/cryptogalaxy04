![](https://github.com/webdevsmart/webdevsmart/blob/main/fullstack.png)

👍 I am a best Full Stack Developer, Database Administrator 👍
I am a Full-Stack developer with years of experience in enterprise and high-performance responsive web technologies for both frontend and backend. Also, I am a self taught Full-Stack Developer, passionate about learning new technologies. I have a working proficiency in JavaScript, React, Redux, HTML, CSS, Node, Express, PGSQL, MongoDB and Sass. I am skilled at making single page applications and progressive web apps with the extended ecosystems that allow your software to operate on multiple devices. I utilize ReactJS, VueJS, AngularJS, HTML5, JavaScript, and other flexible and powerful techniques to create reliable, fast and engaging web apps. I am also skilled at making cost effective cross-platform mobile app development using React Native. I am looking to further expand my skill set by gaining more in depth back-end knowledge. I adapt easily to new challenges and seek solutions to problems that arise sporadically.

.. image:: https://img.shields.io/badge/chat-join%20now-blue.svg
   :target: https://gitter.im/python-trio/general
   :alt: Join chatroom

.. image:: https://img.shields.io/badge/forum-join%20now-blue.svg
   :target: https://trio.discourse.group
   :alt: Join forum

.. image:: https://img.shields.io/badge/docs-read%20now-blue.svg
   :target: https://trio.readthedocs.io
   :alt: Documentation
   
.. image:: https://img.shields.io/pypi/v/trio.svg
   :target: https://pypi.org/project/trio
   :alt: Latest PyPi version

.. image:: https://img.shields.io/conda/vn/conda-forge/trio.svg
   :target: https://anaconda.org/conda-forge/trio
   :alt: Latest conda-forge version   

.. image:: https://codecov.io/gh/python-trio/trio/branch/master/graph/badge.svg
   :target: https://codecov.io/gh/python-trio/trio
   :alt: Test coverage

Trio – a friendly Python library for async concurrency and I/O
==============================================================

.. image:: https://raw.githubusercontent.com/python-trio/trio/9b0bec646a31e0d0f67b8b6ecc6939726faf3e17/logo/logo-with-background.svg
   :width: 200px
   :align: right

The Trio project aims to produce a production-quality,
`permissively licensed
<https://github.com/python-trio/trio/blob/master/LICENSE>`__,
async/await-native I/O library for Python. Like all async libraries,
its main purpose is to help you write programs that do **multiple
things at the same time** with **parallelized I/O**. A web spider that
wants to fetch lots of pages in parallel, a web server that needs to
juggle lots of downloads and websocket connections simultaneously, a
process supervisor monitoring multiple subprocesses... that sort of
thing. Compared to other libraries, Trio attempts to distinguish
itself with an obsessive focus on **usability** and
**correctness**. Concurrency is complicated; we try to make it *easy*
to get things *right*.

Trio was built from the ground up to take advantage of the `latest
Python features <https://www.python.org/dev/peps/pep-0492/>`__, and
draws inspiration from `many sources
<https://github.com/python-trio/trio/wiki/Reading-list>`__, in
particular Dave Beazley's `Curio <https://curio.readthedocs.io/>`__.
The resulting design is radically simpler than older competitors like
`asyncio <https://docs.python.org/3/library/asyncio.html>`__ and
`Twisted <https://twistedmatrix.com/>`__, yet just as capable. Trio is
the Python I/O library I always wanted; I find it makes building
I/O-oriented programs easier, less error-prone, and just plain more
fun. `Perhaps you'll find the same
<https://github.com/python-trio/trio/wiki/Testimonials>`__.

This project is young and still somewhat experimental: the overall
design is solid, and the existing features are fully tested and
documented, but you may encounter missing functionality or rough
edges. We *do* encourage you to use it, but you should `read and
subscribe to issue #1
<https://github.com/python-trio/trio/issues/1>`__ to get a warning and a
chance to give feedback about any compatibility-breaking changes.
