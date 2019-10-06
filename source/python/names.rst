Naming
======

- Use meaningful names
- Avoid, in general, 1 letter names
- Never use ``l``, ``I`` or ``O`` as can be confusing
- Use ascii characters

**No**::

   def my_func(): pass
   def f(): pass

**Yes**::

   def do_nothing(): pass


- Naming styles:

   - ``lower_case_with_underscores``: variables, functions, methods, modules
   - ``CamelCase``: Classes and Exceptions
   - ``_single_leading_underscore(self, ...)``: protected methods and internal functions
   - ``__double_leading_underscore(self, ...)``: private methods
   - ``ALL_CAPS_WITH_UNDERSCORES``: constants

   - Use ``self`` as first argument in methods


- When using abbreviations in ``CamelCase``, capitalize all the letters of the abbreviation

   **No**

   ``HttpServerError``

   **Yes**

   ``HTTPServerError``


- Use trailing underscores to avoid conflicts with reserved keywords instead of abbreviating the name

   **No**::

      class Spam:
          def eggs(clss): pass

   **Yes**::

      class Spam:
         def eggs(class_): pass


- Avoid redundant labelling

   E.g. in the *audio* module

   **No**::

      def audio_play(): ...;

   **Yes**::

      def play(): ...;



- Prefer reverse notations

   **No**::

      elements = ...
      active_element = ...

   **Yes**::

      elements = ...
      elements_active = ...

- avoid abbreviations unless they are de-facto standard

- use complementary names for complementary operations: create/destroy, add/remove, ...

- some booleans can have a special prefix (is-, has-, contains-...)

- try to be positive and avoid negation:

  **No**::

     def is_not_found(): ...

  **Yes**::

     def is_found(): ...

