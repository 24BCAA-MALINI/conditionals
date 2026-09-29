# Dog Breed Identifier

A short Python program that suggests a **herding dog breed** based on two things: the dog's **weight** and its **coat length**.

## How it works

The program uses `if / elif / else` statements to make two decisions:

1. **Weight** picks a size group.
2. **Coat length** picks the breed within that group.

## How to run

1. Install Python 3.
2. Save the code in a file called `dogs.py`.
3. Run:

```bash
python dogs.py
```

Nothing prints until you call a function, so add this at the bottom of the file:

```python
print(identify_dog_breed(25, "short"))
```

Output:

```
Pembroke Welsh Corgi
```

## The function

```python
identify_dog_breed(weight, coat_length)
```

| Parameter | Meaning |
|---|---|
| `weight` | The dog's weight as a number (the code doesn't specify a unit, but the ranges suggest pounds) |
| `coat_length` | A string: `"short"`, `"medium"`, or `"long"` |

**Returns:** the name of the matching breed as a string.

## Breed chart

| Weight | Short coat | Medium coat | Long coat |
|---|---|---|---|
| Under 20 | Swedish Vallhund | Mudi | Shetland Sheepdog |
| 20 to 49 | Pembroke Welsh Corgi | Australian Shepherd | Bearded Collie |
| 50 to 79 | Belgian Malinois | German Shepherd | Collie |
| 80 and over | Beauceron | Bouvier des Flandres | Old English Sheepdog |

## Examples

```python
identify_dog_breed(25, "short")    # Pembroke Welsh Corgi
identify_dog_breed(95, "long")     # Old English Sheepdog
identify_dog_breed(19, "medium")   # Mudi
identify_dog_breed(50, "long")     # Collie
```

Note that a weight of exactly `50` goes in the **50 to 79** group, because the check is `weight < 50`.

## Testing

The program includes `test_identify_dog_breed()`, which checks four cases using `assert`.

| Call | Expected result |
|---|---|
| `identify_dog_breed(25, "short")` | Pembroke Welsh Corgi |
| `identify_dog_breed(95, "long")` | Old English Sheepdog |
| `identify_dog_breed(19, "medium")` | Mudi |
| `identify_dog_breed(50, "long")` | Collie |

The test function only runs if you call it. Add this line at the bottom of the file:

```python
test_identify_dog_breed()
```

If everything passes, you will see:

```
Testing identify_dog_breed...... done!
```

If any check fails, Python stops with an `AssertionError`.

## Notes

- Any `coat_length` other than `"short"` or `"medium"` is treated as **long**. For example, `"Long"` (capital L) or a typo like `"shrt"` will also return the long-coat breed.
- Spelling must match exactly, and it is case-sensitive, so use lowercase.
- Negative or zero weights are not checked and fall into the "under 20" group.
- This is a simple learning example. Real breed identification depends on many more traits than weight and coat.

## Summary

| Item | Detail |
|---|---|
| Language | Python 3 |
| Input | Weight (number) and coat length (string) |
| Output | Breed name (string) |
| Method | Nested `if / elif / else` |
| Dependencies | None |
