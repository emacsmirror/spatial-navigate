######################
Emacs Spatial Navigate
######################

This implements directional navigation `shown here <https://youtu.be/MtDUWcIdu8k>`__.

You may navigate in 4 directions, jumping over contiguous regions of white-space or populated space.

To get an idea how this can be useful it's best to see the demo or try it for yourself.

Motivation
----------

While Emacs has many available methods of navigating based on document structure,
there are times when it's quick & predictable to move the cursor in any direction
jumping between contiguous regions of white-space (or non white-space).

This isn't intended to be better than other methods of navigating between parts of a document,
it's just an alternative which you might find useful.

.. note::

   Single spaces between words are not counted as white-space.


Features
--------

TODO.

Usage
-----

This is not a minor mode, you only need to bind the functions to key bindings.

Available functions:

- ``spatial-navigate-backward-vertical-box``
- ``spatial-navigate-forward-vertical-box``
- ``spatial-navigate-backward-horizontal-box``
- ``spatial-navigate-forward-horizontal-box``
- ``spatial-navigate-backward-vertical-bar``
- ``spatial-navigate-forward-vertical-bar``
- ``spatial-navigate-backward-horizontal-bar``
- ``spatial-navigate-forward-horizontal-bar``

The ``box`` functions detect white space in front and behind the cursor,
while the ``bar`` functions only detect white-space at the cursor and behind it
*(behaving as you might expect when the cursor draws as a bar).*


Example with global key bindings.

.. code-block:: elisp

   (global-set-key (kbd "<M-up>") 'spatial-navigate-backward-vertical-bar)
   (global-set-key (kbd "<M-down>") 'spatial-navigate-forward-vertical-bar)
   (global-set-key (kbd "<M-left>") 'spatial-navigate-backward-horizontal-bar)
   (global-set-key (kbd "<M-right>") 'spatial-navigate-forward-horizontal-bar)


Example with evil-mode key bindings.

.. code-block:: elisp

   (define-key evil-normal-state-map (kbd "M-k") 'spatial-navigate-backward-vertical-box)
   (define-key evil-normal-state-map (kbd "M-j") 'spatial-navigate-forward-vertical-box)
   (define-key evil-normal-state-map (kbd "M-h") 'spatial-navigate-backward-horizontal-box)
   (define-key evil-normal-state-map (kbd "M-l") 'spatial-navigate-forward-horizontal-box)
   (define-key evil-insert-state-map (kbd "M-k") 'spatial-navigate-backward-vertical-bar)
   (define-key evil-insert-state-map (kbd "M-j") 'spatial-navigate-forward-vertical-bar)
   (define-key evil-insert-state-map (kbd "M-h") 'spatial-navigate-backward-horizontal-bar)
   (define-key evil-insert-state-map (kbd "M-l") 'spatial-navigate-forward-horizontal-bar)
