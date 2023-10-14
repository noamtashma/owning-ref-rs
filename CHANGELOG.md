# Changelog

## [0.5.0] - 2023-10-12
This crate has been forked and republished under the name `safer_owning_ref`.

A few soundness problems were fixed - see [#77](https://github.com/Kimundi/owning-ref-rs/issues/77), [#71](https://github.com/Kimundi/owning-ref-rs/issues/71) and [#61](https://github.com/Kimundi/owning-ref-rs/issues/61).

### Changes:
* All types get a new additional lifetime parameter. `OwningRef`, `OwningRefMut` - and all their aliases (such as `BoxRef`).

* `(try_)map_with_owner` functions changed their signatures - now the callback expects a reference to inner type `T` instead of the owner `O`. The old functions are now named `(try_)map_with_owner_direct` and marked deprecated and `unsafe`.
* `From` impl that converts from `OwningRefMut` to `OwningRef` was removed.
* Similarly to the previous point, `OwningRefMut::(try_)map` has been deprecated and marked `unsafe`. That's because it converts from `OwningRef` to `OwningRefMut`. Note that this doesn't effect `(try_)map_mut` or `OwningRef::(try_)map`.
* `Borrow` and `BorrowMut` impls were added.

## [0.4.1] - 2020-02-27
### Added
- `map_with_owner` (#51)

### Changed
- Use dyn for trait objects (#53)
