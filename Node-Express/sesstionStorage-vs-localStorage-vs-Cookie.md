[From Official Dox](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)

The two mechanisms within Web Storage are as follows:

**sessionStorage** maintains a separate storage area for each given origin that's available for the duration of the page session (as long as the browser is open, including page reloads and restores)

**localStorage** does the same thing, but persists even when the browser is closed and reopened.

These mechanisms are available via the Window.sessionStorage and Window.localStorage properties (to be more precise, in supporting browsers the Window object implements the WindowLocalStorage and WindowSessionStorage objects, which the localStorage and sessionStorage properties hang off) — invoking one of these will create an instance of the Storage object, through which data items can be set, retrieved and removed. A different Storage object is used for the sessionStorage and localStorage for each origin — they function and are controlled separately.

localStorage and sessionStorage are perfect for persisting non-sensitive data needed within client scripts between pages (for example: preferences, scores in games). The data stored in localStorage and sessionStorage can easily be read or changed from within the client/browser so should not be relied upon for storage of sensitive or security-related data within applications.

#### So sessionStorage (as the name suggests) is only available for the duration of the browser session (and is deleted when the tab or window is closed) - it does, however, survive page reloads (source DOM Storage guide - Mozilla Developer Network). Clearly, if the data you are storing needs to be available on an ongoing basis then localStorage is preferable to sessionStorage. The data stored in localStorage persists until explicitly deleted. Changes made are saved and available for all current and future visits to the site.

### LocalStorage - Some more details

##### Advantage of localStorage -

##### Disadvantage of localStorage -

1> It works on same-origin policy. So, data stored will only be available on the same origin.

### SessionStorage - Some more details

##### Advantage of sessionStorage -

##### Disadvantage of sessionStorage -

1> The data is available only inside the window/tab in which it was set.

2> Like localStorage, tt works on same-origin policy. So, data stored will only be available on the same origin.

### More General Info

The maximum storage available is different per browser, but most browsers have implemented at least the w3c recommended maximum storage limit of 5MB.

+----------------+--------+---------+-----------+--------+
| | Chrome | Firefox | Safari | IE |
+----------------+--------+---------+-----------+--------+
| LocalStorage | 10MB | 10MB | 5MB | 10MB |
+----------------+--------+---------+-----------+--------+
| SessionStorage | 10MB | 10MB | Unlimited | 10MB |
+----------------+--------+---------+-----------+--------+
Always catch LocalStorage security and quota exceeded errors

QuotaExceededError: When storage limits exceeds on this function window.sessionStorage.setItem(key, value);, it throws a "QuotaExceededError" DOMException exception if the new value couldn't be set. (Setting could fail if, e.g., the user has disabled storage for the site, or if the quota has been exceeded.)

DOMException.QUOTA_EXCEEDED_ERR is 22, example fiddle.

SecurityError : Uncaught SecurityError: Access to 'localStorage' is denied for this document.

CHROME:-Privacy and security « Content settings « Cookies « Block third-party cookies.
StorageEvent « The storage event is fired on a document's Window object when a storage area changes. When a user agent is to send a storage notification for a Document, the user agent must queue a task to fire an event named storage at the Document object's Window object, using StorageEvent.

### Cookie

Compared to others, there's no advantages of Cookies

Stores data that has to be sent back to the server with subsequent requests. Its expiration varies based on the type and the expiration duration can be set from either server-side or client-side (normally from server-side).

Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
Size must be less than 4KB.
Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie
