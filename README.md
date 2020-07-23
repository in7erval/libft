# Libft

---

## What is it?

Libft is a library, that uses only three ***libc*** functions: malloc(3), free(3) and write(2).

---

## Function's_Description

[:arrow_down: To ft_printf](#ft_printf)

| Function | Action | Prototype | Description| Return value |
|:---------:|:-----------|:------- |:-------------|:-------------:|
| ft_memset | Fill block of memory | ```void *ft_memset ( void *ptr, int value, size_t num```); | Sets the first ***num*** bytes of the block of memory pointed by ***ptr*** to the specified value (interpreted as an unsigned char). | Pointer to the memory area ***s***.  |
| ft_bzero | Zero a byte string |```void ft_bzero(void *s, size_t n);```|Erases the data in the ***n*** bytes of the memory starting at the location pointed to by ***s***, by writing zeros (bytes containing '\0') to that area.| None |
| ft_memcpy |Copy memory area|```void *ft_memcpy(void *dest, const void *src, size_t n);```|Copies ***n*** bytes from memory area ***src*** to memory area ***dest***.  The memory areas must not overlap.| Pointer to ***dest***. |
| ft_memccpy |Copy memory area|```void *ft_memccpy(void *dest, const void *src, int c, size_t n);```| Copies no more than ***n*** bytes from memory area ***src*** to memory area ***dest***, stopping when the character ***c*** is found. | Pointer to the next character in ***dest*** after ***c***, or NULL if ***c*** was not found in the first ***n*** characters of ***src***. |
| ft_memmove | Copy memory area|```void *ft_memmove(void *dest, const void *src, size_t n);```| Copies ***n*** bytes from memory area ***src*** to memory area ***dest***.  The memory areas may overlap: copying takes place as though the bytes in ***src*** are first copied into a temporary array that does not overlap ***src*** or ***dest***, and the bytes are then copied from the temporary array to ***dest***. | Pointer to ***dest***.|
| ft_memchr | Scan memory for a character|```void *ft_memchr(const void *s, int c, size_t n);```| Scans the initial ***n*** bytes of the memory area pointed to by ***s*** for the first instance of ***c***.  Both ***c*** and the bytes of the memory area pointed to by ***s*** are interpreted as unsigned char.| Pointer to the matching byte or NULL if the character does not occur in the given memory area.|
| ft_strlen | Calculate the length of a string| ```size_t ft_strlen(const char *s);```|Calculates the length of the string pointed to by ***s***, excluding the terminating null byte ('\0').| Number of bytes in the string pointed to by ***s***.|
| ft_strdup | Duplicate a string|```char *ft_strdup(const char *s);```| Returns a pointer to a new string which is a duplicate of the string ***s***.  Memory for the new string is obtained with malloc(3), and can be freed with free(3).| pointer to the duplicated string.  It returns NULL if insufficient memory was available, with errno set to indicate the cause of the error. |
| ft_strcpy | Copy a string | ```char *ft_strcpy(char *dest, const char *src);```| Copies the string pointed to by ***src***, including the terminating null byte ('\0'), to the buffer pointed to by ***dest***. The strings may not overlap, and the destination string ***dest*** must be large enough to receive the copy.  Beware of buffer overruns! | Pointer to the destination string ***dest***.|
| ft_strncpy | Copy a string | ```char *ft_strncpy(char *dest, const char *src, size_t n);``` | Similar to **ft_strcpy**, except that at most ***n*** bytes of ***src*** are copied.  Warning: If there is no null byte among the first ***n*** bytes of src, the string placed in ***dest*** will not be null-terminated. | Pointer to the destination string ***dest***. |
| ft_strcat | Concatenate two strings | ```char *ft_strcat(char *dest, const char *src);``` | appends the ***src*** string to the ***dest*** string, overwriting the terminating null byte ('\0') at the end of ***dest***, and then adds a terminating null byte.  The strings may not overlap, and the ***dest*** string must have enough space for the result.  If ***dest*** is not large enough, program behavior is unpredictable; buffer overruns are a favorite avenue for attacking secure programs. | Pointer to the resulting string ***dest***. |
| ft_strncat | Concatenate two strings | ```char *ft_strncat(char *dest, const char *src, size_t n);``` | Similar to **ft_strcat**, except that it will use at most ***n*** bytes from ***src*** and ***src*** does not need to be null-terminated if it contains ***n*** or more bytes. | Pointer to the resulting string ***dest***. |
| ft_strlcat | Size-bounded string copying and concatenation | ```size_t ft_strlcat(char *dst, const char *src, size_t size);``` | Similar to **ft_strncat**, but appends the NULL-terminated string ***src*** to the end of ***dst***. It will append at most ```size - ft_strlen(dst) - 1``` bytes, NULL-terminating the result. It's more safer and consistent than **ft_strncat** | Total length of the string they tried to create. |
| ft_strchr | Locate character in string | ```char *ft_strchr(const char *s, int c);``` | Returns a pointer to the first occurrence of the character ***c*** in the string ***s***.| Pointer to the matched character or NULL if the character is not found.  The terminating null byte is considered part of the string, so that if ***c*** is specified as '\0', these functions return a pointer to the terminator. |
| ft_strrchr |Locate character in string|```char *ft_strrchr(const char *s, int c);```| Returns a pointer to the last occurrence of the character ***c*** in the string ***s***. |- " -|
| ft_strstr | Locate a substring | ```char *ft_strstr(const char *haystack, const char *needle);``` | Finds the first occurrence of the substring ***needle*** in the string ***haystack***.  The terminating null bytes ('\0') are not compared. | Pointer to the beginning of the located substring, or NULL if the substring is not found |
| ft_strnstr | Locate a substring in a string | ```char *ft_strnstr (const char *haystack, const char *needle, size_t len);``` | Locates the first occurrence of the null-terminated string ***needle*** in the string ***haystack***, where not more than len characters are searched. Characters that appear after a '\0' character are not searched | If ***needle*** is an empty string, ***haystack*** is returned; if ***needle*** occurs nowhere in ***haystack***, NULL is returned; otherwise a pointer to the first character of the first occurrence of ***needle*** is returned.|
| ft_strcmp | Compare two strings | ```int ft_strcmp(const char *s1, const char *s2);``` | Compares the two strings ***s1*** and ***s2***. Returns an integer indicating the result of the comparison, as follows: - 0, if the ***s1*** and ***s2*** are equal; - a negative value if ***s1*** is less than ***s2***; - a positive value if ***s1*** is greater than ***s2***; | Integer less than, equal to, or greater than zero if ***s1*** (or the first ***n*** bytes thereof) is found, respectively, to be less than, to match, or be greater than ***s2***.|
| ft_strncmp | Compare two strings | ```int ft_strncmp(const char *s1, const char *s2, size_t n);``` | Similar to **ft_strcmp**, except it compares only the first (at most) ***n*** bytes of ***s1*** and ***s2***.|- " -|
| ft_atoi | Convert a string to an integer | ```int ft_atoi(const char *nptr);``` | Converts the initial portion of the string pointed to by ***nptr*** to int. | The converted value. |
| ft_isalpha |Character classification| ```int ft_isalpha(int c);``` | Checks for an alphabetic character | Nonzero if the character ***c*** falls into the tested class, and zero if not. |
| ft_isdigit |Character classification| ```int ft_isdigit(int c);``` | Checks for a digit (0 through 9). |- " -|
| ft_isalnum |Character classification| ```int ft_isalnum(int c);``` | Checks for an alphanumeric character; it is equivalent to ```(ft_isalpha(c) || ft_isdigit(c))```.| - " - |
| ft_isascii |Character classification| ```int ft_isascii(int c);``` | Checks whether ***c*** is a 7-bit unsigned char value that fits into the ASCII character set.| - " - |
| ft_isprint |Character classification| ```int ft_isprint(int c);``` | Checks for any printable character including space. | - " -|
| ft_toupper |Convert uppercase| ```int ft_toupper(int c);``` | Returns its uppercase equivalent, if an uppercase representation exists in the current locale.  Otherwise, it returns ***c***. | The value returned is that of the converted letter, or ***c*** if the conversion was not possible. |
| ft_tolower |Convert lowercase| ```int ft_tolower(int c);``` | Returns its lowercase equivalent, if a lowercase representation exists in the current locale.  Otherwise, it returns ***c***. | - " -|
| ft_memalloc | Allocates memory | ```void *ft_memalloc(size_t size);``` | Allocates (with malloc(3)) and returns a “fresh” memory area. The memory allocated is initialized to 0. If the allocation fails, the function returns NULL. | The allocated memory area. |
| ft_memdel | Free memory | ```void ft_memdel(void **ap);``` | Takes as a parameter the address of a memory area that needs to be freed with free(3), then puts the pointer to NULL. | - |
| ft_strnew | Create string | ```char *ft_strnew(size_t size);``` | Allocates (with malloc(3)) and returns a “fresh” string end- ing with ’\0’. Each character of the string is initialized at ’\0’. If the allocation fails the function returns NULL. | The string allocated and initialized to 0. |
| ft_strdel | Free string | ```void ft_strdel(char **as);``` | Takes as a parameter the address of a string that need to be freed with free(3), then sets its pointer to NULL. | - |
| ft_strclr | Zero string | ```void ft_strclr(char *s);``` | Sets every character of the string to the value ’\0’. | - |
| ft_striter | Apply function to characters in string | void ft_striter(char *s, void (*f)(char *)); | Applies the function f to each character of the string passed as argument. Each character is passed by address to f to be modified if necessary. | - |
| ft_striteri | Apply function to characters in string | ```void ft_striteri(char *s, void (*f)(unsigned int, char *));``` | Applies the function f to each character of the string passed as argument, and passing its index as first argument. Each character is passed by address to f to be modified if necessary. | - |
| ft_strmap | Apply function to characters in string | ```char *ft_strmap(char const *s, char (*f)(char));``` | Applies the function f to each character of the string given as argument to create a “fresh” new string (with malloc(3)) resulting from the successive applications of f. | The “fresh” string created from the successive applications of f. |
| ft_strmapi | Apply function to characters in string | ```char *ft_strmapi(char const *s, char (*f)(unsigned int, char));``` | Applies the function f to each character of the string passed as argument by giving its index as first argument to create a “fresh” new string (with malloc(3)) resulting from the successive applications of f. | The “fresh” string created from the successive applications of f. |
| ft_strequ | Compare strings | ```int ft_strequ(char const *s1, char const *s2);``` | Lexicographical comparison between s1 and s2. If the 2 strings are identical the function returns 1, or 0 otherwise. | 1 or 0 according to if the 2 strings are identical or not. |
| ft_strnequ | Compare strings | ```int ft_strnequ(char const *s1, char const *s2, size_t n);``` | Lexicographical comparison between s1 and s2 up to n char- acters or until a ’\0’ is reached. If the 2 strings are identical, the function returns 1, or 0 otherwise. | 1 or 0 according to if the 2 strings are identical or not. |
| ft_strsub | Create substring from string | ```char *ft_strsub(char const *s, unsigned int start, size_t len);``` | Allocates (with malloc(3)) and returns a “fresh” substring from the string given as argument. The substring begins at indexstart and is of size len. If start and len aren’t refering to a valid substring, the behavior is undefined. If the allocation fails, the function returns NULL. | The substring. |
| ft_strjoin | Join strings | ```char *ft_strjoin(char const *s1, char const *s2);``` | Allocates (with malloc(3)) and returns a “fresh” string ending with ’\0’, result of the concatenation of s1 and s2. If the allocation fails the function returns NULL. **with free of s2!!!!**| The “fresh” string result of the concatenation of the 2 strings. |
| ft_strtrim | Delete whitespaces at beginning end end | ```char *ft_strtrim(char const *s);```| Allocates (with malloc(3)) and returns a copy of the string given as argument without whitespaces at the beginning or at the end of the string. Will be considered as whitespaces the following characters ’ ’, ’\n’ and ’\t’. If s has no whitespaces at the beginning or at the end, the function returns a copy of s. If the allocation fails the function returns NULL. | The “fresh” trimmed string or a copy of s. |
| ft_strsplit | Split string by character | ```char **ft_strsplit(char const *s, char c);``` | Allocates (with malloc(3)) and returns an array of “fresh” strings (all ending with ’\0’, including the array itself) obtained by spliting s using the character c as a delimiter. If the allocation fails the function returns NULL. Example : ft_strsplit("*hello*fellow***students*", ’*’) returns the array ["hello", "fellow", "students"]. | The array of “fresh” strings result of the split. |
| ft_itoa | Convers int to string | ```char *ft_itoa(int n);``` | Allocate (with malloc(3)) and returns a “fresh” string ending with ’\0’ representing the integer ***n*** given as argument. If the allocation fails, the function returns NULL. | The string representing the integer passed as argument. |
| ft_putchar | Output character | ```void ft_putchar(char c); ```| Outputs the character ***c*** to the standard output. | - |
| ft_putstr | Output string | ```void ft_putstr(char const *s);``` | Outputs the string ***s*** to the standard output. | - |
| ft_putendl | Output string | ```void ft_putendl(char const *s);``` | Outputs the string ***s*** to the standard output followed by a ’\n’. | - |
| ft_putnbr | Output number | ```void ft_putnbr(int n);``` | Outputs the integer ***n*** to the standard output. | - |
| ft_putchar_fd | Output character to file descriptor | ```void ft_putchar_fd(char c, int fd);``` | Outputs the char ***c*** to the file descriptor ***fd***. | - |
| ft_putstr_fd | Output string to file descriptor | ```void ft_putstr_fd(char const *s, int fd);``` | Outputs the string ***s*** to the file descriptor ***fd***. | - |
| ft_putendl_fd | Output string to file descriptor | ```void ft_putendl_fd(char const *s, int fd);``` | Outputs the string ***s*** to the file descriptor ***fd*** followed by a ’\n’. | - |
| ft_putnbr_fd | Output number to file descriptor | ```void ft_putnbr_fd(int n, int fd);``` | Outputs the integer ***n*** to the file descriptor ***fd***. | - |
| ft_lstnew | Allocates node | ```t_list *ft_lstnew(void const *content, size_t content_size);``` | Allocates (with malloc(3)) and returns a “fresh” link. The variables ***content*** and ***content_size*** of the new link are initialized by copy of the parameters of the function. If the parameter content is nul, the variable content is initialized to NULL and the variable ***content_size*** is initialized to 0 even if the parameter ***content_size*** isn’t. The variable ***next*** is initialized to NULL. If the allocation fails, the function returns NULL. | The new link. |
| ft_lstdelone | Free node by function | ```void ft_lstdelone(t_list **alst, void (*del)(void *, size_t));``` | Takes as a parameter a link’s pointer address and frees the memory of the link’s content using the function ***del*** given as a parameter, then frees the link’s memory using free(3). The memory of next must not be freed under any circumstance. Finally, the pointer to the link that was just freed must be set to NULL (quite similar to the function ft_memdel in the mandatory part). | - |
| ft_lstdel | Free all nodes by function | ```void ft_lstdel(t_list **alst, void (*del)(void *, size_t));``` | Takes as a parameter the adress of a pointer to a link and frees the memory of this link and every successors of that link using the functions ***del*** and free(3). Finally the pointer to the link that was just freed must be set to NULL. | - |
| ft_lstadd | Add node to list | ```void ft_lstadd(t_list **alst, t_list *new);``` | Adds the element ***new*** at the beginning of the list. | - |
| ft_lstiter | Apply function to each node | ```void ft_lstiter(t_list *lst, void (*f)(t_list *elem));``` | Iterates the list ***lst*** and applies the function ***f*** to each link. | - |
| ft_lstmap | Apply function to each node | ```t_list *ft_lstmap(t_list *lst, t_list *(*f)(t_list *elem));``` | Iterates a list lst and applies the function ***f*** to each link to create a “fresh” list (using malloc(3)) resulting from the successive applications of ***f***. If the allocation fails, the function returns NULL. | The new list. |
| **get_next_line** | Get string from file descriptor | ```int get_next_line(const int fd, char **line);``` | Save **line** from **fd**. | The return value can be 1, 0 or -1 depending on whether a line has been read, when the reading has been completed, or if an error has happened respectively. |

[:arrow_up: To beginning](#Function's_Description)

---
## ft_printf

```c
int ft_printf(char *format, ...);
```
Print **format** string to stdout. (Similar to printf).

Bonus: color print. Example: 
```c
ft_printf("This text will be cyan:{cyan}%s{eoc} red: {red}%s{eoc}", cyanstr, redstr);
``` 
- ***Colors of text***: ```{black}```, ```{red}```, ```{green}```, ```{yellow}```, ```{blue}```, ```{magenta}```, ```{cyan}```.
- ***Colors of background***: ```{black_bg}```, ```{red_bg}```, ```{green_bg}```, ```{yellow_bg}```, ```{blue_bg}```, ```{magenta_bg}```.
- ***Attributes***: ```{bold}```, ```{light}```, ```{underline}```, ```{normal}```, ```{invert}```, ```{hidden}```. ```{eoc}``` - end of color.

Return value: Count of printed characters
