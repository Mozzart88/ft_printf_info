XLOCALE(3) - Library Functions Manual

# NAME

**xlocale** - Extended locale support.

# LIBRARY

Standard C&#160;Library (libc, &#45;lc)

# DESCRIPTION

Include
&lt;xlocale.h&gt;
for extended locale support.
It can be used alone or with the POSIX locale API in
&lt;locale.h&gt;.

The extended locale, or "xlocale" API consists of five basic routines,
which are documented separately:
duplocale(3),
freelocale(3),
newlocale(3),
querylocale(3),
and
uselocale(3).
For each of these routines, if a NULL
*locale\_t*
is given, the current locale is used.

In addition,
&lt;xlocale.h&gt;
defines a few macros:

-	LC\_GLOBAL\_LOCALE - A special
	*locale\_t*
	value that corresponds to the global, process-wide locale.

-	MB\_CUR\_MAX - This macro is traditionally defined as an integer
	containing the value of the longest multi-byte string
	that a single-wide character in the global locale can translate into.
	With extended locales, this macro is replaced with a function
	that returns the value of the longest multi-byte string
	that a single-wide character in the current locale (per-thread or global)
	can translate into.

-	MB\_CUR\_MAX\_L(loc) - This macro is equivalent to MB\_CUR\_MAX,
	except that it may be passed a specific locale directly.

# CAVEATS

The POSIX
setlocale(3)
function only affects the global locale,
so using it when a per-thread locale is in effect
will not change locale behavior for that thread.
However, it will change behavior for threads
with no per-thread locale in effect.

The routines defined in
&lt;rune.h&gt;
are deprecated, and may not be fully consistent with the xlocale API.
Of particular note is
**setinvalidrune**(),
which would normally modify the value in the global locale.
Since this value resides in a sub-structure of
*locale\_t*
and sub-structures may be shared by multiple locales,
**setinvalidrune**()
has been modified to make a copy of the sub-structure.
This prevents it from affecting other locales.

# SEE ALSO

duplocale(3),
freelocale(3),
localeconv(3),
newlocale(3),
querylocale(3),
uselocale(3)

# CONVENIENCE FUNCTIONS

The xlocale API also includes "convenience functions":
functions that can be executed using a given locale,
rather than the current locale.
These functions all take one extra
*locale\_t*
argument at the end of the traditional argument list,
except in the case of variable-argument functions,
in which case the extra argument comes before the format string.
If a NULL
*locale\_t*
is passed, the C locale will be used.

For completeness,
the convenience functions are listed here
(organized by the header file that contains the original function).

&lt;\_wctype.h&gt;

> iswalnum\_l(3),
> iswalpha\_l(3),
> iswcntrl\_l(3),
> iswctype\_l(3),
> iswdigit\_l(3),
> iswgraph\_l(3),
> iswlower\_l(3),
> iswprint\_l(3),
> iswpunct\_l(3),
> iswspace\_l(3),
> iswupper\_l(3),
> iswxdigit\_l(3),
> towlower\_l(3),
> towupper\_l(3),
> wctype\_l(3)

&lt;ctype.h&gt;

> digittoint\_l(3),
> isalnum\_l(3),
> isalpha\_l(3),
> isblank\_l(3),
> iscntrl\_l(3),
> isdigit\_l(3),
> isgraph\_l(3),
> ishexnumber\_l(3),
> isideogram\_l(3),
> islower\_l(3),
> isnumber\_l(3),
> isphonogram\_l(3),
> isprint\_l(3),
> ispunct\_l(3),
> isrune\_l(3),
> isspace\_l(3),
> isspecial\_l(3),
> isupper\_l(3),
> isxdigit\_l(3),
> tolower\_l(3),
> toupper\_l(3)

&lt;inttypes.h&gt;

> strtoimax\_l(3),
> strtoumax\_l(3),
> wcstoimax\_l(3),
> wcstoumax\_l(3)

&lt;langinfo.h&gt;

> nl\_langinfo\_l(3)

&lt;monetary.h&gt;

> strfmon\_l(3)

&lt;stdio.h&gt;

> asprintf\_l(3),
> fprintf\_l(3),
> fscanf\_l(3),
> printf\_l(3),
> scanf\_l(3),
> snprintf\_l(3),
> sprintf\_l(3),
> sscanf\_l(3),
> vasprintf\_l(3),
> vfprintf\_l(3),
> vfscanf\_l(3),
> vprintf\_l(3),
> vscanf\_l(3),
> vsnprintf\_l(3),
> vsprintf\_l(3),
> vsscanf\_l(3)

&lt;stdlib.h&gt;

> atof\_l(3),
> atoi\_l(3),
> atol\_l(3),
> atoll\_l(3),
> mblen\_l(3),
> mbstowcs\_l(3),
> mbtowc\_l(3),
> strtod\_l(3),
> strtof\_l(3),
> strtol\_l(3),
> strtold\_l(3),
> strtoll\_l(3),
> strtoq\_l(3),
> strtoul\_l(3),
> strtoull\_l(3),
> strtouq\_l(3),
> wcstombs\_l(3),
> wctomb\_l(3)

&lt;string.h&gt;

> strcoll\_l(3),
> strxfrm\_l(3),
> strcasecmp\_l(3),
> strcasestr\_l(3),
> strncasecmp\_l(3)

&lt;time.h&gt;

> strftime\_l(3),
> strptime\_l(3)

&lt;wchar.h&gt;

> btowc\_l(3),
> fgetwc\_l(3),
> \*fgetws\_l(3),
> fputwc\_l(3),
> fputws\_l(3),
> fwprintf\_l(3),
> fwscanf\_l(3),
> getwc\_l(3),
> getwchar\_l(3),
> mbrlen\_l(3),
> mbrtowc\_l(3),
> mbsinit\_l(3),
> mbsnrtowcs\_l(3),
> mbsrtowcs\_l(3),
> putwc\_l(3),
> putwchar\_l(3),
> swprintf\_l(3),
> swscanf\_l(3),
> ungetwc\_l(3),
> vfwprintf\_l(3),
> vfwscanf\_l(3),
> vswprintf\_l(3),
> vswscanf\_l(3),
> vwprintf\_l(3),
> vwscanf\_l(3),
> wcrtomb\_l(3),
> wcscoll\_l(3),
> wcsftime\_l(3),
> wcsnrtombs\_l(3),
> wcsrtombs\_l(3),
> wcstod\_l(3),
> wcstof\_l(3),
> wcstol\_l(3),
> wcstold\_l(3),
> wcstoll\_l(3),
> wcstoul\_l(3),
> wcstoull\_l(3),
> wcswidth\_l(3),
> wcsxfrm\_l(3),
> wctob\_l(3),
> wcwidth\_l(3),
> wprintf\_l(3),
> wscanf\_l(3)

&lt;wctype.h&gt;

> iswblank\_l(3),
> iswhexnumber\_l(3),
> iswideogram\_l(3),
> iswnumber\_l(3),
> iswphonogram\_l(3),
> iswrune\_l(3),
> iswspecial\_l(3),
> nextwctype\_l(3),
> towctrans\_l(3),
> wctrans\_l(3)

&lt;xlocale.h&gt;

> localeconv\_l(3)

Mac OS X 10.12 - March 11, 2005
