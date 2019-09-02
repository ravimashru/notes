# encodeURI vs encodeURIComponent

Used to escape characters in a string reserved for URLs.



As a rule of thumb,

- `encodeURIComponent` is used to encode parts of a URL (for example, a query string parameter).
- `encodeURI` is used to encode an entire URL.



`encodeURI` does not encode characters that have a special meaning for a URI.

`encodeURIComponent` escapes all characters except: `A-Z a-z 0-9 - _ . ! ~ * ' ( )`.



**Examples:**

| **String**                                       | **encodeURI**                                        | **encodeURIComponent**                                       |
| ------------------------------------------------ | ---------------------------------------------------- | ------------------------------------------------------------ |
| `https://www.google.com`                         | `https://www.google.com`                             | `https%3A%2F%2Fwww.google.com`                               |
| `https://www.myserver.com/page=a new dream.html` | `https://www.myserver.com/page=a%20new%20dream.html` | `https%3A%2F%2Fwww.myserver.com%2Fpage%3Da%20new%20dream.html` |
| `123.com/abc#def`                                | `123.com/abc#def`                                    | `123.com%2Fabc%23def`                                        |

