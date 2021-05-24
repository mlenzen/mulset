# Mulset

## Why?

* I've been frustrated with Python collections for a long time [1]_ [2]_
	- Too much cognitive overhead
	- Incomplete functionality
* Too many combinations of collection attributes to comprehend, code or maintain distinctly
	- unique
	- ordered
	- indexed
	- mutable
	- value restrictions (hashable -> fast contains check)
	- default values / generators / functions
	- multi-value mappings
* Consistent APIs
	- `add` or `remove` to all collections
* Inheriting from and extending list, dict, set ... is non-idiomatic

.. _[1]: https://mail.python.org/archives/list/python-ideas@python.org/thread/DOGT3OG57ZAQYJECUR27GUV5QM5HVWZL/
.. _[2]: https://github.com/mlenzen/collections-extended/blob/master/HISTORY.rst

### How

* Collection functionality must be composed and the mechanics hidden behind the scenes ("collections for humans")

## What's Different

- Mappings are simpler, they are Collections of tuples
- Mappings have `keys` and `values` that are MulSet views which can also be unique, ...
	* Specify values collection type?
- Consistency between collections
	* e.g. they all have `.add`
		- for lists this is append
		- for dicts this is adding a tuple
	*
- Abstract store
	* shared core API could be more explicitly mutable under

- Need to abstract away the store so that Mapping views can easily do everything the MulSet proper can
- Everything is ordered?
	* Just by default?
