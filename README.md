# The C* Programming Language

C* is a lightweight syntax extension that transpiles to standard C, improving code readability and developer experience.

## Quick Start

The following `cst` file transpiles to the valid `c` code below it.

```c
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

typedef struct User {
  int id;
  char *name;
  int age;
} User;

impl User {
  Self new(char *name, int age) {
    int id = rand();
    return (User) {id, name, age};
  }

  bool is_adult(User user) {
    return user.age >= 18;
  }
}

int main(void) {
  User user = User::new("Tom", 21);

  if (user.is_adult()) {
    printf("User %s is an adult.", user.name);
  }

  return 0;
}
```

```c
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

typedef struct User {
  int id;
  char *name;
  int age;
} User;

User User_new(char *name, int age) {
    int id = rand();
    return (User) {id, name, age};
}

bool User_is_adult(User user) {
    return user.age >= 18;
}

int main(void) {
  User user = User_new("Tom", 21);

  if (User_is_adult(user)) {
    printf("User %s is an adult.", user.name);
  }

  return 0;
}
```
