# 🎤 Appendix D: Viva Questions with Short Answers

> **BCA Web Technology — Oral Examination Guide**  
> Topic-wise important viva questions ke clear English + Hinglish answers.

---

## 🎯 Viva Answer Karne Ka Best Formula

Har answer ko 3 parts mein boliye:

1. **Definition** — term kya hai?
2. **Purpose** — kyun use hoti hai?
3. **Example** — project/code se one example.

Example:

> “A primary key table ki har row ko uniquely identify karti hai. Yeh duplicate aur null identity ko prevent karti hai. Mere students table mein `student_id` primary key hai.”

### Viva Tips

- Pehle direct answer dein, phir explanation.
- Full form exact boliye.
- “Mujhe nahi pata” ke badle guess na karein; jo related concept pata hai woh honestly batayein.
- Apne project ka code and database khud explain karna aana chahiye.
- Security question mein frontend validation ko sufficient na batayein.
- Diagram ko left-to-right flow mein explain karein.

---

# 1. 🌐 Internet, Web and HTTP Viva

### 1. Internet kya hai?

Internet globally connected computer networks ka system hai jo standard protocols se data exchange karta hai.

### 2. World Wide Web kya hai?

WWW internet par available interlinked web pages and resources ka system hai, commonly HTTP/HTTPS se access hota hai.

### 3. Internet aur Web mein difference kya hai?

Internet underlying network infrastructure hai; Web internet par chalne wali services mein se one service hai.

### 4. Client kya hota hai?

Client device/software server se resource or service request karta hai, जैसे web browser.

### 5. Server kya hota hai?

Server requests receive karke pages, data, files or application services provide karta hai.

### 6. Client–server architecture ka flow kya hai?

Client request bhejta hai, server process karta hai, zarurat par database use karta hai and response return karta hai.

### 7. Protocol kya hai?

Protocol communication ke standardized rules ka set hai, जैसे HTTP.

### 8. IP address kya hai?

IP address network par device/interface ko identify and route karne wala numeric address hai.

### 9. Domain name kya hai?

Domain human-readable internet name hai, जैसे `example.com`, jo DNS se IP address par resolve hota hai.

### 10. DNS kya karta hai?

DNS — Domain Name System — domain names ko IP addresses and related records se map karta hai.

### 11. URL kya hai?

URL — Uniform Resource Locator — web resource ka location/address describe karta hai.

### 12. URL ke main parts kya hain?

Scheme, host/domain, optional port, path, query string and fragment.

### 13. HTTP kya hai?

HTTP — Hypertext Transfer Protocol — client and server ke beech request/response communication rules define karta hai.

### 14. HTTPS kya hai?

HTTPS TLS-protected HTTP hai jo transit confidentiality, integrity and server authentication support karta hai.

### 15. HTTP request ke parts kya hain?

Method/target, headers and optional body.

### 16. HTTP response ke parts kya hain?

Status code, response headers and optional body.

### 17. GET aur POST mein difference kya hai?

GET resource read karta hai; POST commonly data submit/create/process karta hai. GET safe/read-only semantics follow karna chahiye.

### 18. 200, 201, 404 and 500 ka meaning kya hai?

200 success, 201 resource created, 404 resource not found and 500 unexpected server error.

### 19. Cookie kya hai?

Cookie browser mein stored small name–value data hai jo requests ke saath server ko bheji ja sakti hai.

### 20. Session kya hai?

Session multiple requests ke across user-related state maintain karti hai, commonly random session ID ke through.

---

# 2. 🧱 HTML and Accessibility Viva

### 21. HTML ka full form kya hai?

HTML — HyperText Markup Language.

### 22. HTML programming language hai?

HTML markup language hai; yeh content ka structure and meaning define karti hai, general-purpose programming logic नहीं.

### 23. Tag aur element mein difference kya hai?

Tag markup marker hai, जैसे `<p>`; element complete structure hai—tags, attributes and content.

### 24. Attribute kya hai?

Attribute element ko extra information/configuration deta hai, जैसे anchor ka `href`.

### 25. Semantic HTML kya hai?

Meaningful elements such as `header`, `nav`, `main` and `article` use karna semantic HTML hai.

### 26. Semantic HTML ke benefits kya hain?

Accessibility, code readability, browser understanding and search discoverability improve ho sakti hai.

### 27. `div` aur `section` mein difference kya hai?

`div` generic container hai; `section` thematic section ko represent karta hai, usually heading ke saath.

### 28. Block and inline elements kya hain?

Block element typically new line/full available width behavior rakhta hai; inline content text flow mein rehta hai. CSS display behavior change kar sakti hai.

### 29. `id` aur `class` mein difference kya hai?

`id` document mein unique identifier ke liye; `class` reusable grouping/styling ke liye.

### 30. Form mein `name` attribute kyun required hai?

Submit hone par control ka key `name` banta hai; name ke bina value usually form data mein include nahi hoti.

### 31. GET form and POST form kab use karenge?

Search/filter जैसे safe shareable request ke liye GET; data create/change or sensitive body ke liye POST with server security.

### 32. Label ka purpose kya hai?

Label input ka accessible name and larger clickable association provide karta hai.

### 33. `alt` attribute kya hai?

Image ka text alternative hai; image purpose/content ko screen readers or failed loading state mein explain karta hai.

### 34. Decorative image ka alt kya hona chahiye?

Usually empty alt: `alt=""`, taaki assistive technology unnecessary description skip kare.

### 35. Table mein `caption` and `scope` kyun use hote hain?

Caption table purpose batata hai; scope header ko corresponding row/column cells se associate karta hai.

### 36. Accessibility kya hai?

Web content ko disabilities सहित widest users ke liye perceivable, operable, understandable and robust banana.

### 37. ARIA kya hai?

ARIA — Accessible Rich Internet Applications — assistive technology ko additional semantics/states provide karta hai.

### 38. ARIA कब use karni chahiye?

Jab native semantic HTML required meaning/behavior provide na kare; native HTML ko prefer karna chahiye.

### 39. Keyboard accessibility kaise check karenge?

Tab/Shift+Tab, Enter, Space and arrow keys se all actions and visible focus test karenge.

### 40. `aria-live` ka use kya hai?

Dynamic status updates ko screen reader users ke liye announce karne mein help karta hai.

---

# 3. 🎨 CSS Viva

### 41. CSS ka full form kya hai?

CSS — Cascading Style Sheets.

### 42. CSS rule ke parts kya hain?

Selector plus declaration block; declaration property and value se banti hai.

### 43. Cascade kya hai?

Cascade conflicting styles mein origin, importance, layers, specificity and source order se winning declaration choose karta hai.

### 44. Specificity kya hai?

Selector priority weight hai jo competing rules mein apply hone wali rule decide karne mein help karta hai.

### 45. Inheritance kya hai?

Kuch CSS properties parent element se children ko automatically milti hain, जैसे text color.

### 46. Box model kya hai?

Content, padding, border and margin milkar CSS box model banate hain.

### 47. Margin and padding mein difference kya hai?

Padding content aur border ke beech inner space; margin border ke outside space.

### 48. `box-sizing: border-box` kya karta hai?

Declared width/height mein padding and border include karta hai.

### 49. Flexbox kab use karte hain?

One-dimensional row or column alignment/layout ke liye.

### 50. Grid kab use karte hain?

Two-dimensional rows and columns based layouts ke liye.

### 51. `justify-content` and `align-items` mein difference kya hai?

Flex/Grid context mein justify main axis and align cross axis ko control karta hai; exact axes writing mode/layout par depend karte hain.

### 52. Relative and absolute positioning ka relation kya hai?

Absolute element nearest positioned ancestor ke respect mein place hota hai; parent `position: relative` reference establish kar sakta hai.

### 53. Sticky position kya hai?

Element normal flow mein rehta hai, then specified scroll boundary par sticky behave karta hai.

### 54. Responsive design kya hai?

Layout/content ko different viewport sizes and device capabilities ke according usable banana.

### 55. Media query kya hai?

CSS condition hai jo viewport/media feature ke according rules apply karti hai.

### 56. Mobile-first design kya hai?

Base styles small screens ke liye, then minimum-width queries se larger layouts enhance karna.

### 57. `rem` and `em` mein difference kya hai?

`rem` root font size relative; `em` current element/related computed font size context relative.

### 58. Transition and animation compare karein.

Transition state change ke beech interpolation; animation keyframes se multiple timed states independently run kar sakti hai.

### 59. `transform` animation kyun prefer hoti hai?

Transform often layout recalculation reduce karke smoother rendering support kar sakta hai, though actual performance measure karni chahiye.

### 60. `prefers-reduced-motion` kya hai?

User ki reduced motion preference detect karke animations reduce/disable karne ki media feature.

---

# 4. 🟨 JavaScript Viva

### 61. JavaScript kya hai?

JavaScript web platform ki programming language hai jo logic, DOM interaction and asynchronous communication provide karti hai.

### 62. `var`, `let` and `const` compare karein.

`var` function-scoped/legacy behavior; `let` block-scoped reassignable; `const` block-scoped and binding reassigned nahi hoti.

### 63. JavaScript primitive types kya hain?

String, number, bigint, boolean, undefined, symbol and null.

### 64. `null` and `undefined` mein difference kya hai?

`null` intentional empty value; `undefined` value absent/unassigned ko represent karta hai.

### 65. `==` and `===` compare karein.

`==` type coercion kar sakta hai; `===` type and value strict compare karta hai.

### 66. Function kya hai?

Reusable code block jo parameters receive and value return kar sakta hai.

### 67. Parameter and argument mein difference kya hai?

Parameter function definition ka input name; argument function call mein actual passed value.

### 68. Arrow function kya hai?

Compact function syntax with lexical `this` behavior; har method/constructor use case ke liye same nahi.

### 69. Array kya hai?

Ordered indexed values ka collection.

### 70. Object kya hai?

Key–value properties and methods ka collection.

### 71. `map()` and `filter()` compare karein.

`map()` every element transform karke same-length new array; `filter()` condition pass karne wale elements ki new array.

### 72. `find()` and `filter()` mein difference kya hai?

`find()` first matching value/undefined; `filter()` all matches ki array.

### 73. `reduce()` kya karta hai?

Array values ko accumulator ke through single result—sum/object/group—mein combine karta hai.

### 74. DOM kya hai?

Document Object Model page ka tree-like programmable representation hai.

### 75. `querySelector()` kya karta hai?

CSS selector match karne wala first element return karta hai, or null.

### 76. Event kya hai?

Browser/user occurrence, जैसे click, input, submit or load.

### 77. Event bubbling kya hai?

Event target se ancestor elements ki taraf propagate ho sakta hai.

### 78. Event delegation kya hai?

Parent listener se descendant events handle karna, usually bubbling and target matching se.

### 79. `preventDefault()` kya karta hai?

Event ka default browser action रोकता hai, propagation necessarily नहीं.

### 80. `stopPropagation()` kya karta hai?

Event ka further propagation रोकता hai; default action अलग concept hai.

### 81. Promise kya hai?

Future asynchronous operation result represent karta hai with pending, fulfilled and rejected states.

### 82. `async` function kya return karti hai?

Async function always Promise return karti hai.

### 83. `await` kya karta hai?

Current async function ki execution ko promise settle hone tak pause karke fulfillment value deta hai.

### 84. Fetch API kya hai?

Promise-based browser API jo HTTP requests bhejti and Response objects process karti hai.

### 85. Fetch 404 par automatically reject hoti hai?

Usually nahi; network failure reject hota hai, but HTTP error ke liye `response.ok`/status check karna hota hai.

### 86. JSON parse and stringify kya karte hain?

`JSON.parse()` JSON text to JS value; `JSON.stringify()` JS value to JSON text.

### 87. Optional chaining kya hai?

`?.` nested property/method ko safely access karta hai; nullish value par undefined return kar sakta hai.

### 88. Nullish coalescing kya hai?

`??` left value null or undefined hone par fallback deta hai.

### 89. Module kya hai?

Import/export ke through isolated reusable JavaScript file/unit.

### 90. Exception handling ka syntax kya hai?

`try` risky code, `catch` error handling and optional `finally` cleanup.

---

# 5. 🛠️ Bootstrap, Tools and Git Viva

### 91. Bootstrap kya hai?

Bootstrap responsive CSS/JavaScript components and utility classes wala frontend framework hai.

### 92. Bootstrap grid ka basic structure kya hai?

Container → row → columns; grid responsive breakpoints/classes use karta hai.

### 93. Browser DevTools ka use kya hai?

DOM/CSS inspect, console errors, network requests, storage, accessibility and performance debug karna.

### 94. Git kya hai?

Git distributed version-control system hai jo source changes and history track karta hai.

### 95. GitHub kya hai?

Git repositories host/collaborate/manage karne wali online platform.

### 96. Repository kya hai?

Project files plus Git history ka collection.

### 97. Commit kya hai?

Staged changes ka named/history snapshot.

### 98. Branch kya hai?

Independent development line jo main history se changes isolate karti hai.

### 99. Merge kya hai?

One branch/history ke changes dusri branch mein combine karna.

### 100. Pull request kya hai?

Proposed branch changes ko review and merge karne ka collaboration request/workflow.

### 101. `git clone` and `git pull` compare karein.

Clone first complete repository copy banata hai; pull existing local repo mein remote updates fetch and integrate karta hai.

### 102. Merge conflict kya hai?

Jab Git competing changes automatically combine nahi kar pata and manual resolution required hoti hai.

---

# 6. 🐘 PHP and Back-End Viva

### 103. PHP ka full form kya hai?

PHP: Hypertext Preprocessor.

### 104. Server-side language kya hoti hai?

Code server par execute hota hai and client ko generated response milta hai.

### 105. PHP variable ka syntax kya hai?

Dollar sign and name, जैसे `$name = 'Aditi';`.

### 106. Indexed and associative array compare karein.

Indexed array numeric keys; associative array named keys use karti hai.

### 107. `include` and `require` mein difference kya hai?

Missing include warning ke baad continue ho sakta hai; missing require fatal error se script stop karta hai.

### 108. Superglobal kya hai?

PHP built-in array jo scopes mein accessible hoti hai, जैसे `$_POST`, `$_SERVER`.

### 109. `$_GET` and `$_POST` compare karein.

`$_GET` query-string parameters; `$_POST` standard form body data contain karta hai.

### 110. Server validation kyun required hai?

Client validation bypass ho sakti hai; server authoritative trust boundary hai.

### 111. `htmlspecialchars()` ka use kya hai?

HTML output context mein special characters encode karke untrusted text ko markup banne se rokne mein help karta hai.

### 112. Cookie and session compare karein.

Cookie browser-stored value; session server-maintained state with browser session identifier.

### 113. Login ke baad session ID regenerate kyun karte hain?

Session fixation risk reduce karne ke liye.

### 114. Password plain text mein kyun nahi store karte?

Database leak par all passwords immediately exposed ho jayenge.

### 115. `password_hash()` and `password_verify()` kya karte hain?

First adaptive hash create; second input password ko stored hash against verify karta hai.

### 116. CSRF token kya hai?

Session-bound unpredictable value jo state-changing request legitimacy verify karne mein help karta hai.

### 117. File upload secure kaise karenge?

Authorization, CSRF, size/type content checks, random filename, isolated storage and safe serving.

### 118. OOP kya hai?

Object-Oriented Programming classes/objects ke through data and behavior organize karta hai.

### 119. Class and object compare karein.

Class blueprint; object class ka actual instance.

### 120. Encapsulation kya hai?

Internal state and implementation ko controlled methods/access levels ke through protect/organize karna.

### 121. Inheritance kya hai?

Child class parent class se accessible behavior/properties reuse/extend karti hai.

### 122. Polymorphism kya hai?

Common interface/method contract ke through different implementations behave kar sakti hain.

### 123. Interface kya hai?

Class implementations ke required public methods ka contract.

### 124. Constructor kya hai?

Object creation par initialization ke liye called special method.

### 125. Exception handling kya hai?

Runtime failures ko `try/catch/finally` se controlled way mein manage karna.

---

# 7. 🗄️ Database, SQL and PDO Viva

### 126. Database kya hai?

Related data ka organized collection jo efficiently store and manage hota hai.

### 127. DBMS and RDBMS compare karein.

DBMS database manage karta hai; RDBMS relational tables and relationships based DBMS hai.

### 128. SQL ka full form kya hai?

Structured Query Language.

### 129. Table, row and column kya hain?

Table structure; row one record; column record attribute/field.

### 130. Schema and instance compare karein.

Schema database blueprint; instance particular time ka actual data.

### 131. Primary key kya hai?

Column(s) jo every row ko uniquely identify and null/duplicate identity prevent karti hain.

### 132. Foreign key kya hai?

Child column(s) jo parent key reference karke referential integrity enforce karti hain.

### 133. Candidate and alternate key kya hain?

Candidate minimal unique key; selected primary ke alawa candidate alternate key.

### 134. Composite key kya hai?

Multiple columns ki combined key.

### 135. Constraint kya hai?

Database-level data rule, जैसे NOT NULL, UNIQUE, CHECK or FOREIGN KEY.

### 136. One-to-many relationship example kya hai?

One course has many students; foreign key students table mein ho sakti hai.

### 137. Many-to-many relationship kaise implement hoti hai?

Junction table with both foreign keys and suitable unique/composite key.

### 138. Normalization kya hai?

Tables ko organize karke redundancy and update anomalies reduce karna.

### 139. 1NF kya hai?

Cells atomic values contain karein and repeating groups absent hon.

### 140. 2NF kya hai?

1NF plus non-key attributes composite key ke whole par depend karein.

### 141. 3NF kya hai?

2NF plus non-key attribute dusre non-key attribute par transitively depend na kare.

### 142. CRUD ka full form kya hai?

Create, Read, Update, Delete.

### 143. DELETE, TRUNCATE and DROP compare karein.

DELETE rows; TRUNCATE all rows; DROP table structure and data remove karta hai. Exact transaction behavior DBMS-specific ho sakta hai.

### 144. WHERE and HAVING compare karein.

WHERE grouping se pehle rows filter; HAVING grouping ke baad groups filter.

### 145. INNER JOIN kya return karta hai?

Both joined sides par matching rows.

### 146. LEFT JOIN kya return karta hai?

All left-table rows plus right matches; no match par right columns null.

### 147. Self join kya hai?

Same table ko different aliases/roles mein khud se join karna.

### 148. Cross join kya hai?

Both tables ke all possible row combinations.

### 149. Index kya hai?

Lookup data structure jo reads help kar sakti hai but storage and writes cost add karti hai.

### 150. Transaction kya hai?

Related database operations ka logical all-or-nothing unit.

### 151. ACID ka full form kya hai?

Atomicity, Consistency, Isolation and Durability.

### 152. COMMIT and ROLLBACK compare karein.

COMMIT transaction changes permanent; ROLLBACK uncommitted transaction changes undo.

### 153. PDO kya hai?

PHP Data Objects database access interface hai with prepared statements and transactions.

### 154. Prepared statement kya hai?

SQL template jisme data parameters separately bind/execute hote hain, injection risk reduce hota hai.

### 155. `fetch()` and `fetchAll()` compare karein.

`fetch()` one row; `fetchAll()` all remaining rows memory mein return karta hai.

### 156. `lastInsertId()` kya karta hai?

Current connection ke last generated auto-increment-like ID ko return kar sakta hai.

---

# 8. ⚡ AJAX, JSON, XML and API Viva

### 157. AJAX ka full form kya hai?

Asynchronous JavaScript and XML.

### 158. AJAX ka main benefit kya hai?

Full page reload ke bina server communication and partial UI update.

### 159. Kya AJAX mein XML compulsory hai?

Nahi; JSON, HTML, text and other formats use ho sakte hain.

### 160. Promise ki states kya hain?

Pending, fulfilled and rejected.

### 161. Debounce kya hai?

Rapid repeated events ke baad delay se final function run karna, request count reduce karne ke liye.

### 162. Race condition kya hai?

Async operations unexpected order mein finish hokar stale result latest state overwrite kar de.

### 163. AbortController ka use kya hai?

Fetch जैसी supported operations ko cancellation signal dena.

### 164. JSON kya hai?

Language-independent lightweight text data format with objects, arrays and basic value types.

### 165. Valid JSON mein property keys kaise likhi jati hain?

Double-quoted strings ke रूप में.

### 166. XML kya hai?

Extensible Markup Language custom-tag hierarchical text data/document format hai.

### 167. Well-formed and valid XML compare karein.

Well-formed syntax correct; valid additionally defined schema/DTD rules follow karta hai.

### 168. XML namespace kya hai?

Different XML vocabularies ke same names ko URI-based identity se distinguish karta hai.

### 169. API kya hai?

Application Programming Interface software components ke communication contract/operations define karta hai.

### 170. REST kya hai?

Representational State Transfer distributed hypermedia system architectural style hai.

### 171. Resource and endpoint compare karein.

Resource conceptual entity; endpoint us resource/action ka accessible method + URI.

### 172. Stateless API ka meaning kya hai?

Each request mein necessary request context ho; server prior conversational request context par depend na kare.

### 173. PUT and PATCH compare karein.

PUT commonly complete replacement; PATCH partial modification.

### 174. 401 and 403 compare karein.

401 valid authentication absent/invalid; 403 identity known but permission denied.

### 175. CORS kya hai?

Browser cross-origin requests/read access ko server headers se control karne ka mechanism.

### 176. Webhook kya hai?

Event hone par provider consumer ke registered URL ko server-to-server request bhejta hai.

---

# 9. 🔐 Web Security Viva

### 177. CIA triad kya hai?

Confidentiality, Integrity and Availability.

### 178. Threat, vulnerability and risk compare karein.

Threat possible harm; vulnerability weakness; risk likelihood and impact ka evaluated combination.

### 179. Defense in depth kya hai?

Multiple independent security layers use karna taaki one control fail par others protect karein.

### 180. Authentication and authorization compare karein.

Authentication identity; authorization allowed actions/resources decide karta hai.

### 181. SQL injection kya hai?

Untrusted input SQL query structure/meaning modify kar de.

### 182. SQL injection ka primary defense kya hai?

Parameterized/prepared statements plus least privilege.

### 183. XSS kya hai?

Untrusted content browser mein executable markup/script context mein run ho jaye.

### 184. XSS kaise prevent karenge?

Context-aware output escaping, safe DOM APIs, trusted sanitization when HTML required and CSP as extra defense.

### 185. CSRF kya hai?

Attacker victim ke authenticated browser se unwanted state-changing request trigger karwata hai.

### 186. CSRF prevention kya hai?

Framework protection or session-bound token, SameSite cookie and server verification.

### 187. HTTPS kya protect karta hai?

Client-server transit confidentiality, integrity and server identity; application bugs automatically fix nahi karta.

### 188. Least privilege kya hai?

User/process/database ko only minimum required permissions dena.

### 189. Secure cookie attributes kya hain?

`Secure`, `HttpOnly` and suitable `SameSite`, plus appropriate path/domain/lifetime.

### 190. CSP kya hai?

Content Security Policy browser ko allowed content sources and other restrictions batati hai.

### 191. SSRF kya hai?

Server ko attacker-chosen/internal destinations par request karne ke liye misuse karna.

### 192. Error details user ko kyun hide karte hain?

Stack trace, query, paths and credentials जैसी sensitive implementation information leak ho sakti hai.

### 193. Security logs mein passwords/token kyun nahi rakhte?

Logs compromise/access hone par secrets directly expose ho jayenge.

### 194. Backup restore test kyun important hai?

Backup file ka exist karna enough nahi; successful recovery capability prove honi chahiye.

---

# 10. 🚀 Performance, SEO and PWA Viva

### 195. Web performance kya hai?

Page loading, responsiveness, visual stability and user-perceived speed ka quality area.

### 196. Lab and field data compare karein.

Lab controlled reproducible test; field real users/devices/networks data.

### 197. LCP kya measure karta hai?

Largest Contentful Paint loading performance; main large content kab visible hua.

### 198. INP kya measure karta hai?

Interaction to Next Paint user interaction responsiveness.

### 199. CLS kya measure karta hai?

Cumulative Layout Shift unexpected visual movement/stability.

### 200. Image dimensions kyun specify karte hain?

Browser space reserve karke layout shifts reduce karta hai.

### 201. Lazy loading kya hai?

Noncritical resource ko immediately ke badle need/near-viewport par load karna.

### 202. CDN kya hai?

Content Delivery Network geographically distributed nodes se content closer/faster deliver kar sakta hai.

### 203. SEO kya hai?

Search engines ko content discover/understand and users ko relevant pages find/choose karne mein help karna.

### 204. Crawling and indexing compare karein.

Crawling pages discover/download; indexing content analyze/store.

### 205. Canonical URL kya hai?

Duplicate/similar page variants ke preferred URL ka signal/hint.

### 206. robots.txt security control hai?

Nahi; it is crawler directive file. Sensitive data authentication/authorization se protect hota hai.

### 207. XML sitemap kya hai?

Important canonical URLs ki machine-readable list jo discovery support karti hai; indexing guarantee nahi.

### 208. PWA kya hai?

Progressive Web Application modern web capabilities se enhanced reliable/installable web app ho sakti hai.

### 209. Manifest kya karta hai?

Installed web app ka name, icons, start URL, scope and display metadata provide karta hai.

### 210. Service worker kya karta hai?

Browser-managed worker jo scoped network requests and background events handle kar sakta hai.

### 211. Cache-first and network-first compare karein.

Cache-first cache preference; network-first fresh network response, failure par cache fallback.

### 212. IndexedDB kya hai?

Browser ka structured persistent local database API.

---

# 11. 🎓 Final Project Viva

### 213. Aapke project ka problem statement kya hai?

One sentence mein current problem, affected users and proposed portal solution explain karein.

### 214. Technology stack kyun choose kiya?

HTML/CSS UI, JavaScript interaction, PHP server logic and MySQL relational data ke requirement-fit explain karein.

### 215. Functional and non-functional requirements compare karein.

Functional app kya karta hai; non-functional security, performance, accessibility, reliability जैसी quality define karta hai.

### 216. Project architecture explain karein.

Browser request → PHP controller → validation/authorization → service/repository → MySQL → escaped HTML/JSON response.

### 217. ER diagram mein main relationships kya hain?

Actual project entities and 1:1, 1:M or M:N relations with foreign keys explain karein.

### 218. Database normalize kyun ki?

Duplicate data and insert/update/delete anomalies reduce karne ke liye related entities separate tables mein rakhi.

### 219. User roles kaise enforce kiye?

Session identity plus server-side route/action/record authorization; UI link hiding only convenience.

### 220. CRUD operations kahan implement hain?

Create form/INSERT, list/detail SELECT, edit/UPDATE and protected POST delete/DELETE route show karein.

### 221. SQL injection kaise prevent ki?

All untrusted values PDO prepared statements se execute and dynamic identifiers allowlist kiye.

### 222. XSS kaise prevent ki?

HTML output `htmlspecialchars()` and JavaScript DOM text `textContent` se render kiya.

### 223. CSRF kaise prevent ki?

Session-bound random token forms mein include and server par `hash_equals()` se validate kiya.

### 224. Password and session kaise secure ki?

`password_hash()`/`password_verify()`, HTTPS, secure cookie settings and login par session ID regeneration.

### 225. AJAX feature kya hai?

Live search/form action ka request, JSON response, loading/error handling, debounce and cancellation explain karein.

### 226. API design kaise ki?

Noun resources, HTTP methods, status codes, JSON shapes, pagination, validation and authorization explain karein.

### 227. File upload kaise secure ki?

Size and detected MIME allowlist, random filename, private storage, authorization and safe serving.

### 228. Transaction kahan use ki?

Dependent records—user plus student/enrollment/audit—atomic create; failure par rollback.

### 229. Error handling kaise ki?

User ko generic message/status, developer log mein safe diagnostic, transaction cleanup.

### 230. Performance kaise measure/improve ki?

DevTools/Lighthouse, optimized images/assets, pagination, `EXPLAIN` and query-driven indexes.

### 231. Accessibility kaise check ki?

Semantic HTML, labels, keyboard focus, contrast, responsive zoom and screen-reader/status tests.

### 232. Project test cases kya hain?

Happy path, invalid inputs, boundary, authorization, security, database failure, mobile and performance cases.

### 233. Git kaise use kiya?

Feature branches/meaningful commits, pull/review workflow and secrets-excluding `.gitignore` explain karein.

### 234. Deployment mein kya steps hain?

HTTPS, environment secrets, restricted DB user, migrations, public web root, debug off, backups and smoke tests.

### 235. Project limitation kya hai?

Actual missing/non-implemented feature honestly state karein—e.g. MFA or automated coverage—plus impact.

### 236. Future scope kya hai?

Prioritized next feature and uska user benefit, security and technical plan explain karein.

### 237. Agar database down ho jaye to app kya karega?

Connection exception log, generic 500/503-like response, no secrets, monitoring/alert and recovery procedure.

### 238. Agar same form twice submit ho to kya hoga?

PRG, disabled button, unique constraint and transaction/idempotency design duplicate effect reduce karte hain.

### 239. Aapke project ka strongest security control kya hai?

One control ko “complete security” na boliye; defense-in-depth—authorization, prepared SQL, escaping, CSRF, sessions—explain karein.

### 240. Project se sabse important learning kya hui?

Design-to-deployment full request flow and security/testing decisions ko concrete example se explain karein.

---

# 12. ⚡ Rapid-Fire One-Line Viva

| Question | One-Line Answer |
|---|---|
| HTML? | Page structure and semantics |
| CSS? | Presentation and layout |
| JavaScript? | Browser logic and interactivity |
| PHP? | Server-side scripting |
| MySQL? | Relational database system |
| Git? | Distributed version control |
| API? | Software communication interface |
| JSON? | Lightweight structured data format |
| Primary key? | Unique row identity |
| Foreign key? | Parent-child relationship constraint |
| CRUD? | Create, Read, Update, Delete |
| DOM? | Programmable document tree |
| AJAX? | Background HTTP and partial update |
| PDO? | PHP database access interface |
| XSS defense? | Context-aware output escaping |
| SQLi defense? | Prepared statements |
| CSRF defense? | Session-bound token |
| Password storage? | Adaptive password hash |
| 404? | Resource not found |
| 403? | Permission denied |
| REST? | Distributed-system architectural style |
| LCP? | Loading metric |
| INP? | Interaction metric |
| CLS? | Visual stability metric |
| PWA? | Progressively enhanced web app |

---

## ✅ Viva Self-Test Checklist

- [ ] All important full forms bol sakta/sakti hoon?
- [ ] Client–server request flow draw kar sakta/sakti hoon?
- [ ] HTML, CSS and JavaScript roles compare kar sakta/sakti hoon?
- [ ] PHP form → PDO → MySQL flow explain kar sakta/sakti hoon?
- [ ] Keys, normalization and joins examples de sakta/sakti hoon?
- [ ] Authentication and authorization clear hain?
- [ ] SQL injection, XSS and CSRF defenses clear hain?
- [ ] AJAX/JSON/API response flow clear hai?
- [ ] Performance and SEO difference clear hai?
- [ ] Apne project ka ER diagram and code explain kar sakta/sakti hoon?
- [ ] Limitations honestly bata sakta/sakti hoon?
- [ ] Live demo backup ready hai?

---

## 🔁 5-Minute Viva Revision

```text
Browser → HTTP Request → PHP
PHP → Validate + Authorize + CSRF
PHP → PDO Prepared SQL → MySQL
MySQL → Result → PHP
PHP → Escape HTML / Encode JSON
Browser → Render + DOM + Events

Security:
Authentication ≠ Authorization
Validation ≠ Escaping
HTTPS ≠ Secure Code
Frontend Check ≠ Server Security

Database:
PK → Identity
FK → Relationship
JOIN → Related data
Transaction → All or nothing

Performance:
LCP → Load
INP → Interaction
CLS → Stability
```

---

[⬅️ Previous: Appendix C](c-practical-programs.md) · [📚 Table of Contents](../SUMMARY.md) · **Next: Appendix E — Important Exam Questions ➡️**
