# license_type

> Auto-generated documentation for [licensematrix.license_type](../../licensematrix/license_type.py) module.

Represent a license.

- [Licensematrix_](../README.md#licensematrix_-index) / [Modules](../README.md#licensematrix_-modules) / [licensematrix](index.md#licensematrix) / license_type
    - [License](#license)
        - [License().\_\_repr\_\_](#license__repr__)
        - [License().\_\_str\_\_](#license__str__)
        - [License().isCopyleft](#licenseiscopyleft)
        - [License().isPermissive](#licenseispermissive)
        - [License().isPublicDomain](#licenseispublicdomain)
        - [License().isViral](#licenseisviral)
        - [License().isWeakCopyleft](#licenseisweakcopyleft)
        - [License().mergeBoth](#licensemergeboth)
        - [License().mergeIntoDest](#licensemergeintodest)
        - [License().naiveCompatDest](#licensenaivecompatdest)
        - [License().naiveCompatSource](#licensenaivecompatsource)
    - [equal](#equal)
    - [getMostStrictType](#getmoststricttype)
    - [mergeSPDX](#mergespdx)

Source: represents an existing license
Dest: represents a new combined license (possibly for a combined work)

## License

[[find in source code]](../../licensematrix/license_type.py#L12)

```python
class License():
    def __init__(
        name: str = '',
        title: str = '',
        shortName: str = '',
        tags: Optional[list[str]] = None,
        must: Optional[list[str]] = None,
        cannot: Optional[list[str]] = None,
        can: Optional[list[str]] = None,
        typeIn: str = '',
        spdx: str = '',
        fromDict: Optional[dict[(str, Any)]] = None,
    ):
```

Represent a license.

Source: represents an existing license
Dest: represents a new combined license (possibly for a combined work)

### License().\_\_repr\_\_

[[find in source code]](../../licensematrix/license_type.py#L61)

```python
def __repr__() -> str:
```

Get the string representation.

### License().\_\_str\_\_

[[find in source code]](../../licensematrix/license_type.py#L65)

```python
def __str__() -> str:
```

To string.

### License().isCopyleft

[[find in source code]](../../licensematrix/license_type.py#L77)

```python
def isCopyleft():
```

Is the License Copyleft?

### License().isPermissive

[[find in source code]](../../licensematrix/license_type.py#L69)

```python
def isPermissive():
```

Is the License Permissive?

### License().isPublicDomain

[[find in source code]](../../licensematrix/license_type.py#L85)

```python
def isPublicDomain():
```

Is the License Public Domain?

### License().isViral

[[find in source code]](../../licensematrix/license_type.py#L81)

```python
def isViral():
```

Is the License Viral?

### License().isWeakCopyleft

[[find in source code]](../../licensematrix/license_type.py#L73)

```python
def isWeakCopyleft():
```

Is the License Weak Copyleft?

### License().mergeBoth

[[find in source code]](../../licensematrix/license_type.py#L89)

```python
def mergeBoth(rhs: License):
```

Combine two licenses into one super license.

Performs no checks on compatibility, this is up to the user.

#### Arguments

- `rhs` *License* - the other license to merge

#### Returns

- `License` - the new, combined license

### License().mergeIntoDest

[[find in source code]](../../licensematrix/license_type.py#L106)

```python
def mergeIntoDest(dest: License):
```

Combine two licenses into one super license, but preserve the...

destination name. Performs no checks on compatibility, this is up to the user.

#### Arguments

- `dest` *License* - the other license to merge

#### Returns

- `License` - the new, combined license

### License().naiveCompatDest

[[find in source code]](../../licensematrix/license_type.py#L144)

```python
def naiveCompatDest(dest: License) -> bool:
```

Check the source (self) is compatible with the destination license (rhs).

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the licenses compatible?

### License().naiveCompatSource

[[find in source code]](../../licensematrix/license_type.py#L122)

```python
def naiveCompatSource(dest: License) -> bool:
```

Check the destination (rhs) is compatible with the source license (self).

#### Arguments

- `dest` *License* - the destination license

#### Returns

- `bool` - are the licenses compatible?

## equal

[[find in source code]](../../licensematrix/license_type.py#L204)

```python
def equal(licenseA: License, licenseB: License) -> bool:
```

Are two licenses equal?

#### Arguments

- `licenseA` *License* - the first license
- `licenseB` *License* - the second license

#### Returns

- `bool` - equal?

#### See also

- [License](#license)

## getMostStrictType

[[find in source code]](../../licensematrix/license_type.py#L169)

```python
def getMostStrictType(typeA: str, typeB: str) -> str:
```

Return the most 'strict' type of license from the available types.

#### Arguments

- `typeA` *str* - type of the first license
- `typeB` *str* - type of the second license

#### Returns

- `str` - the most 'strict' type

## mergeSPDX

[[find in source code]](../../licensematrix/license_type.py#L187)

```python
def mergeSPDX(spdxA: str, spdxB: str) -> str:
```

Combine the spdx ids.

#### Arguments

- `spdxA` *str* - spdx of the first license
- `spdxB` *str* - spdx of the second license

#### Returns

- `str` - combined spdx