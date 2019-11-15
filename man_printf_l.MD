PRINTF\_L(3) - Library Functions Manual

# NAME

**`asprintf\_l`**,
**`dprintf\_l`**,
**`fprintf\_l`**,
**`printf\_l`**,
**`snprintf\_l`**,
**`sprintf\_l`**,
**`vasprintf\_l`**,
**`vdprintf\_l`**,
**`vfprintf\_l`**,
**`vprintf\_l`**,
**`vsnprintf\_l`**,
**`vsprintf\_l`** - formatted output conversion

# LIBRARY

Standard C Library (libc, -lc)

# SYNOPSIS

**#include <stdio.h>**  
**#include <xlocale.h>**

*int*  
**`asprintf_l`**(*char `**ret`*, *locale\_t `loc`*, *const char `*format`*, *...*);

*int*  
**`dprintf_l`**(*int `fd`*, *locale\_t `loc`*, *const char `* restrict format`*, *...*);

*int*  
**`fprintf_l`**(*FILE `* restrict stream`*, *locale\_t `loc`*, *const char `* restrict format`*, *...*);

*int*  
**`printf_l`**(*locale\_t `loc`*, *const char `* restrict format`*, *...*);

*int*  
**`snprintf_l`**(*char `* restrict str`*, *size\_t `size`*, *locale\_t `loc`*, *const char `* restrict format`*, *...*);

*int*  
**`sprintf_l`**(*char `* restrict str`*, *locale\_t `loc`*, *const char `* restrict format`*, *...*);

**#include <stdarg.h>**  
**#include <xlocale.h>**

*int*  
**`vasprintf_l`**(*char `**ret`*, *locale\_t `loc`*, *const char `*format`*, *va\_list `ap`*);

*int*  
**`vdprintf_l`**(*int `fd`*, *locale\_t `loc`*, *const char `* restrict format`*, *va\_list `ap`*);

*int*  
**`vfprintf_l`**(*FILE `* restrict stream`*, *locale\_t `loc`*, *const char `* restrict format`*, *va\_list `ap`*);

*int*  
**`vprintf_l`**(*locale\_t `loc`*, *const char `* restrict format`*, *va\_list `ap`*);

*int*  
**`vsnprintf_l`**(*char `* restrict str`*, *size\_t `size`*, *locale\_t `loc`*, *const char `* restrict format`*, *va\_list `ap`*);

*int*  
**`vsprintf_l`**(*char `* restrict str`*, *locale\_t `loc`*, *const char `* restrict format`*, *va\_list `ap`*);

# DESCRIPTION
The **`printf_l`**(), **`dprintf_l`**(), **`fprintf_l`**(), **`sprintf_l`**(), **`snprintf_`l**(), **`asprintf_l`**(), **`vprintf_l`**(), **`vdprintf_l`**(), **`vfprintf_l`**(), **`vsprintf_`l**(), **`vsnprintf_l`**(), and **`vasprintf_l`**() functions are extended locale versions of the **`printf`**(), **`dprintf`**(), **`fprintf`**(), **`sprintf`**(), **`snprintf`**(), **`asprint`f**(), **`vprintf`**(), **`vdprintf`**(), **`vfprintf`**(), **`vsprintf`**(), **`vsnprintf`**(), and **`vasprintf`**() functions, respectively. Refer to their manual pages for details. Also, see xlocale(3) for more information about extended locales.

# SEE ALSO
**printf**(3), **xlocale**(3)

Mac OS X 10.12 - December 15, 2009
