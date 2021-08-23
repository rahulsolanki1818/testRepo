# Code Review

## <ins>Table Of Contents:</ins>

1. [Clean Code](https://github.com/rahulsolanki1818/testRepo/blob/master/README.md#clean-code)
2. Security
3. Performance
4. Implement CI/CD
5. Unit Test

## <ins>Clean Code:</ins>

### `1. Use Intention-Revealing Names:`

Use self-explanatory words for functions, variables, classes etc.

**References:**

1. Make use of the full name i.e. `getDateDifference` instead of `getDateDiff`.  (line no. `30`).
2. Arguments name should not be like `dateA` & `dateB`. The date can be `lastDate` & `today`.  (line no. `30`).
3. Screen component name should be similar to file name i.e. `Home`. (line no. `34`).

**Severity:** Medium

### `2. Don't Repeat Yourself (Avoid Duplication):`

Code redundancy should be avoided. Segregate the component to reduce the number of repetitions for the component.
**`Home.JSX`**

**References:**

1. Create a function for getting `activeButton` colour.
2. Create a separate component for `VictoryBar`, instead of repeating it. And pass varying `values` as props.

**Severity:** Medium

### `3. Make Sure The Code Formatting Is Applied:`

Configure and follow the linting strictly. Make use of `eslint` for restricting the linting rules. Add pre-commit hook for checking linting errors on git.

**References:
`Home.JSX`**

1. Unexpected mix of `-` and `%`. Use parentheses to clarify the intended order of operations. (line no `43`) 
2. the `summary` is already declared in the upper scope on line 36 column 10. (line no. `47`)
3. Unary operator `++` used. (line no. `48`)
4. Array.prototype.map() expects a value to be returned at the end of the arrow function. (line no. `59`, `68`)

**Severity:** Medium

### `4. Move HardCoded Strings To Constant File:`

Segregate the `HardCoded` string in a single place or in a `Constant` directory.

**References:
`Home.JSX`**

1. dayNames can be segregated and can be kept in a constant file. (line no. `11`)
2. Hardcoded strings of the chart tab should be kept as a javascript object in a constant file. (line no. `35`).

**Severity:** Medium

### `Note:`
I have the following checklist to be considered while reviewing the code:

- Take your time. Don't rush.
- Review every line.
- Don't hesitate to communicate with the developer in case of any queries.
- Properly review the changes again, after an iteration.

---

## <ins>Security:</ins>

### `1. Avoid excessive logs for unusual behaviour:`

**References:** NA

**Severity:** Medium

### `2. Document security-related information:`

**References:** NA

**Severity:** Medium

### `3. Do not log highly sensitive information:`

**References:** NA

**Severity:** High

### `4. Define wrappers around native methods (not declare a native method public):`

**References:** NA

**Severity:** Medium

### `5. Release resources (Event Listeners, Connections, etc) in all cases:`

Make sure to remove `eventListeners` on `componentDidMount` in case of `class component` & on `useEffect` in case of `functional components`.

**References:** NA

**Severity:** Medium

### 6. **`Make Use of Encrypted Storage For Storing Key-Value Pair:`**

`Async Storage` is unencrypted, key-value store. It should only be used for storing information, which doesn't require encryption. 

**References:** NA
**Severity:** High

---

## <ins>Performance:</ins>

### `1. Follow semantic defined by ReactJS:`

**References:** 

1. Home screen's `useEffect` hook is calling continuously because it doesn't contain the dependency array as a second argument. And it set's the summary via the `setSummary` method. Which triggers `useEffect` continuously due to the component's state update. And app stops responding to touch events completely.

    > `useEffect` without dependency works as `componentDidUpdate` in terms of the class component. (line no. `38`).

2. Move inline `styles` to separate files or top/bottom of the component using `Stylesheet.create`. (line no. `81`)

**Severity:** Medium

### `2. Avoid using unnecessary imports:`

Remove unnecessary imports from the files to speed up the app start up time.

**References:** NA

**Severity:** Medium


---

## **<ins>Implement CI/CD</ins>**

### **`1. CI/CD Setup For Build Automation & Test:`**

Integrate `Fastlane` pipeline for generating build using the command line. And add CI/CD for build automation using any of the CI/CD providers. Use any of the providers `CircleCI`, `TravisCI` or `BitRise`.

- **References:** NA
- **Severity:** Medium

---

## **<ins>Unit Test</ins>**

### `1. Valid Jest Test Cases For UI & Logic:`

Implement UI testing & Logic testing to make sure the addition of any new feature doesn't affect the other part or existing feature of the app.

**References:** NA

**Severity:** Medium

# <ins>Strategic Thinking</ins>

### `Documentation:`

Documentation is an important aspect of product designing. A well-documented product help to get a glimpse of features, code or product's overview very easily. In the same way from the code perspective, well-documented code and integrated feature details can help people from the team & also to a new team member. Define a document on product features, implementation.

### `User Retention:`

Understanding the lifetime behaviour patterns churned users had before they walk away from your product can help you identify variations from your more loyal customers. Analysing overall product engagement and retention or drilling down into feature usage will give you a more specific picture of churned user interaction.

### `Analytics (User Tracking):`

Analytics helps to track the user's activity in the app. We can determine which feature of the app is mostly used by the users. And accordingly, we can create the user funnels too. We can determine the whole user journey map and can turn the user into a customer. This can help to know the user's needs & implement the unknown use cases.

### `Performance:`

While other sources described above is necessary to convert users to customer. Meanwhile, performance is most necessary to maintain the customer for long. Performance app is loved by customers and this opens the opportunity for mouth-to-mouth promotion.

**`Here is some way that can make the UX engaging & better:`**

1. **Avoid Showing Loading Indicator:** Render the content that you already have as soon as a new screen is opened and display a loader and/or some placeholder component while the content is loading (Same as the Facebook app). This is a technic known as Skeleton Screens.
2. If your click leads to something like Adding an item to your cart, to favourites or post a chat message. This very often includes a remote API call. In that case, you should when act as the endpoint did already respond successfully. This pattern is called Optimistic UI and is also widespread across the industry.
3. Images are the hard part to handle in the app. Proper caching & expiring of the content is necessary when developing the app. To be free from this responsibility from our end, we can use react-native-fast-image and resize the image according to need. This will improve the UX & performance drastically.
4. Don't use HOCs (Higher Order Components) on the fly.
5. Make use of `State Management (Redux)` for holding run time data (If Needed).

---

## `Project Tracking:`

We can track the progress of the project by utilising Project Management Tools like `Atlassian`, `Trello`, `GitHub Projects`, `Linear`. And We can follow agile methodology. i.e.

- Daily Scrum.
- Monthly spring planning.
- Weekly Sprint Grooming.
- Weekly Retrospective Meeting.

So that all the team members should stay on the same plane.

---

## `Communication:`

For effective project management, communication plays an important role. So we can use the below tools:

- Slack
- Discord
- MatterMost
- etc.
