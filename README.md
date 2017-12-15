# Orus PHP Style Guidelines
The Orus team PHP coding standards


This document describes PHP Style Guidelines for Orus projects.

### Overview

The following set of guidelines describes the coding styles adhered to when crafting Orus's applications using PHP. Every member of the Orus team must follow these set of rules.

### Most Important
- Use PHP only as a programming language, not a templating language.
- Avoid globals.
- Avoid `extract()`, `eval()`.
- Avoid variable variables.
- Always prefer classes over functions.
- Prefer class constants over defines.
- Avoid naked class properties; instead, define accessors.
- Use exceptions for error conditions.
- Use type hints, use `assert_instance_of()` for arrays holding objects.

### Language Style
- Files should always be saved with UTF-8 encoding.
- Use `<?php`, not the `<?` short form.
- Omit the closing `?>` tag.
- The class namespace declaration must be on the same line as the class name.
- Function and control structures must use Allman style braces.
- Prefer casts like `(string)` to casting functions like `strval()`.
- Avoid type functions like `is_null()`, prefer type checks like `$label === null`.
- Please avoid any form of language constructs like `endif` and `<>`.
- Always put braces around conditional and loop blocks.
- Avoid `else` when there is no need.
- **Do not** use switch statement in your code.

### Spaces, Linebreaks and Indentation
- Don't use tab literal characters.
- Use two spaces for indentation.
- Use Unix linebreaks `\n`, not MSDOS `\n\r` or OS9 `\r`.
- Put a space after control keywords like `if` and `for`.
- Put a space after commas in argument lists.
- Always put a space around operators like `=`, `<`, `>` etc.
- Do not put space after function names.
- Parentheses should hug their contents.
- Generally, prefer to wrap code at 80 columns.
- Put a space before and after the `!` operator.

### Comments
- Do not use `#` (shell-style) comments.
- Prefer single line comment `//` inside functions and methods bodies.

### Case and Capitalization
- Name variables and functions using `lowercase_with_inderscore`.
- Always name class using `UpperCamelCase`.
- Use uppercase for common accronyms like ID and HTML.
- Name constants using `UPPERCASE`
- Always write `true`, `false` and `null` in lowercase.

### Examples

**if/else:**
```
if ($something)
{
    return '...';
}
return '...';
```

**`!`** operator
```
if ( ! $something)
{
    return '...';
}
```
Always put braces around the body of an if clause, even if it is only one line long. You can also notice spaces around operators and after control statements. And please do not use the "endif" construct, and write "else if" as two words.

**for:**
```
for ($ii = 0; $ii < 3; $ii++)
{
    // ...
}
```
Prefer $ii, $jj, $zz, etc., as iterators, because they're easier to pick out visually and they react better to "Find Next..." in editors.

**foreach:**
```
foreach $map as $key => $value)
{
    // ...
}
```

**arrays:**
```
$fruits = [
    'orange',
    'banana',
    'apple',
];
```
Use a trailing comma and put the closing parenthesis on a separate line so that diffs which add elements to the array affect only one line.

**operators:**
```
$a + $b;                 // Put spaces around operators.
$some . $thing;          // Put spaces around string concatenation.
$bucket[] = $element;    // Couple [] with the array when appending.
$obj = new Fruit;        // Parentheses can be optional.
```

**function/method definitions:**
```
function do_something($base_value, $additional_value)
{
    return $base_value + $additional_value;
}

class Foo {
  public static function doSomething(Bazz $base)
  {
      // do something
  }
}
```

**class**
```
class Student extends Person {

    const MAXIMUM_ATTEMPTS = 3;
    
    private $age = 19;
    
    public function getAge()
    {
        return $this->age;
    }
}
```
