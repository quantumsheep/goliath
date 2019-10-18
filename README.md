# Goliath
Header-only extended, fast and reliable C data types library.

# Data types
Actually Goliath contains those implementations:
- Vector (automatic dynamic arrays)
- Key-Value map

## Vector
Vectors are automatic dynamic arrays, which means that it will allocate the necessary memory without your help.

### Initializing
You must initialize a vector before using it.

```c
Vector *vec = vector_init();
```

### Pushing a value
You can push absolutely anything to a vector. Some `push` functions does something special.

`vector_push` will **copy** the content of a given pointer into a new vector's index. It performs a `memcpy` so it needs the size of the pointer.
```c
typedef struct a_t A;
struct a_t
{
    int value;
};

A *array = malloc(sizeof(A) * 5);

vector_push(vec, array, sizeof(A) * 5);
```
