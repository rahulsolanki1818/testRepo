## <ins>Table Of Contents:</ins>

1. [Clean Code](#clean-code)
2. [Strategic Thinking](#strategic-thinking)

# Code Review
### **1. Avoid Duplication:**

- **Issue:** There is a logic code duplicacy while assigning the *color* to Buttons.</br>
![4](https://i.ibb.co/T4rWkSq/1.png)</br>
**Remedy:** Create a function for getting *activeButton* colour.</br></br>

- **Issue:** There is `VictoryBar` component repetition in render method when only source (Y) prop is changing.</br>
**Remedy:** Create a separate component for `VictoryBar`, instead of repeating it. And pass varying *values* as props.</br></br>


### **2. Meaningful Names:**

- **Issue:** Function's argument names should be self-explanatory:  (`line 30`)</br>
**Remedy:** `dateA` & `dateB` can be renamed as *lastDate* & *currentDate*.</br></br>

- **Issue:** The screen name should indicate the file name.</br>
![](https://i.ibb.co/4RHX0p1/2.png)</br>
**Remedy:** Can be renamed from `Victory` to `Home`.</br></br>
- **Issue:** Do not use a shortcut i.e. `getDateDiff`.</br>
![](https://i.ibb.co/18qYXJt/3.png)</br>
**Remedy:** Can be renamed as *getDateDifference*.</br></br>

### **3. Constant File:**

- **Issue:** dayNames can be kept in a constant file.  (`line 11`)</br>
- **Issue:** Javascript object can be created for Hardcoded strings of the chart tab in a constant file. (`line 35`)</br>
**Remedy:** Keep the HardCoded string in a Constant directory.</br></br>

### **4. Code Formatting:**

- **Issue:** In the Array.prototype.map() function return value is expected at the end of the arrow function.  (`line 59`)</br>
- **Issue:** The summary is already declared in the upper scope on line 36 column 10.  (`line 46`)</br>
- **Issue:** The order of operations is not clear, use parentheses.  (`line 43`)</br></br>
**Remedy:** Configure linting extensions like eslint. Add pre-commit hook for checking linting errors on git.</br></br>

### **5. Performance:**

- **Issue:** Home screen's useEffect hook doesn't contain the dependency array as a second argument. Which triggers useEffect continuously due to the component's state update. useEffect without dependency works as componentDidUpdate in terms of the class component.</br>
![](https://i.ibb.co/Pm66LnW/4.png)</br>
**Remedy:** Pass dependancy array as second argument of useEffect.</br></br>
- **Issue:** Inline styles are used. (`line 80`)</br>
**Remedy:** Stylesheet.create object can be used.</br></br>

### **6. Logical:**

- **Issue:** Code is written considering only three sources (hustles). Since I don't have much knowledge around business logic, but I assume it can vary with the users. So logic should be written in dynamic way, which can accept multiple sources (hustles).</br>
![](https://i.ibb.co/fpvD3W4/5.png)</br>
**Remedy:** Dynamic data source (hustles) must be used to support multiple side hustles.</br>.</br>
- **Issue:** Data is misaligned on `VictoryGraph`. Indexing is not proper, it is behind the *-1* i.e. Data of *Monday* is showing at *Sunday* and same implies for other days as well.</br>
![](https://i.ibb.co/N9x8x1f/6.png)</br>
**Remedy:** Due to superficial knowledge of the project, there can be multiple solutions. Like:</br>
- Either we can change Graph Representation or fix the logic.</br>
</br></br>
---
# Strategic Thinking

### **1. Project Management:**

For effective project management, we can use agile methodology. i.e.

- Daily Status Update.
- PR Code Review.
- Spring Planning.
  - Grooming.
  - Retrospective.
- Build Release Plan.</br>

**Why?** Planning is the most important part for any product success. We should have proper project planning so that the team can be aligned toward the big picture and the goals we're trying to achieve. 
</br></br>

### **2. Performance:**

**Here is some way that can make the UX engaging & better:**

1. Unnecessary network call should be avoided.
2. UI shouldn't be blocked for the user. Avoid using too many loaders.
3. UI should be updated instantly and functional operations should be performed after words.</br>

**Why?** Performance plays an important role for any app success & compete in the market.
</br></br>

### **3. Design:**
1. Design should be pixel perfect as per given design (Abstract, Figma etc.).
2. Make use of SVGs to reduce the bundle size.</br>

**Why?** The first thing you need to attract your users is cool visuals. If you can create a mobile app consisting of great visuals, infographics, proper theme colors, it is bound to attract the users’ attention at the first go.</br></br>

### **4. Project documentation**:

*Project documentation* is the process of recording the key project details and producing the documents that are required to implement it successfully. Simply put, it's an umbrella term which includes all the documents created over the course of the project.
Project documents come in many forms – from project proposals and business cases, to project plans and project status reports.</br></br>

---
