Angular SDK for Plone
=====================

In this chapter, we will learn how to use the `Plone Angular SDK <https://www.npmjs.com/package/@plone/restapi-angular>`_ to build easily single-page app sites based on the :doc:`./restapi`.

What is Angular
---------------

`Angular <https://angular.io/>`_ is a JavaScript framework released in 2016.

- It is component-oriented.
- It is shipped with RxJS, the Reactive Programming library.
- It works with TypeScript, a superset of EcmaScript 6, which allows a cleaner coding.
- It provides a powerful CLI to build projects.

It makes it a very good framework which is both powerful and easy to use. 

.. note::

  Angular was initially known as Angular 2 as AngularJS was its ancestor.
  Angular and AngularJS are very different, but their name are quite close so when looking for packages, verify carefully which Angular it is compliant with.

What is the Plone Angular SDK
-----------------------------

The Plone Angular SDK is an Angular package (named ``@plone/restapi-angular`` as it belongs to the Plone NPM organization).

It is a high-level integration layer between Angular and the Plone RESTAPI.

It provides:

- services to dialog with the Plone backend,
- ready-to-use components (for instance ``<plone-navigation>`` or ``<plone-breadcrumbs>``),
- traversing.

Traversing
----------

Traversing is a key feature when working with CMS.
Angular core, like the other major JS frameworks, uses routing.
It works perfectly for applications, but it is not applicable for web sites (as the site structure is not predictable).

The Traversal service based on `Angular traversal <https://github.com/makinacorpus/angular-traversal>`_ replaces the default Angular routing. It uses the current location to determine the backend resource (the **context**) and the desired rendering (the **view**).

The view is the last part of the current location and is prefixed by `@@`.
If no view is specified, it defaults to `view`.

The rest of the location is the resource URL.

Example: `/news/what-about-traversal/@@edit`

When traversing to the location, the resource will be requested to the backend, and the result will become the current context, accessible from any component in the app.

According the values in the `@type` property of the context, the appropriate component will be used to render the view.

.. note::

  We can also use another criteria than `@type` by registring a custom marker (the package comes with an `InterfaceMarker` which marks context according the `interfaces` attribute, which is supposed to be a list. At the moment, the Plone REST API does not expose this attribute).

A new integration approach for Plone
------------------------------------



Installing the development environment
--------------------------------------

Initializing a new project
--------------------------

Using and customizing the Angular Plone components
--------------------------------------------------

Integrating a full theme
------------------------

Creating a custom component
---------------------------

Creating a custom view
----------------------

Deploying as a static site
--------------------------

Deploying as a server-side rendered site
----------------------------------------
