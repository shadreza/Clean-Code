# Clean-Code
this is from shihab vai

# Clean Code Guide

 ## Whitespace

* Spaces, not tabs, are the white space character of choice in our projects. Tabs should consist of 4 spaces.

* Comma, colon, and semicolon characters always get a single space after them and never before them.
  ```js
  // bad
  [1,2,3]

  // good
  [1, 2, 3]
  ```
* Binary arithmetic operators, equals sign, arrows always get a single space before and after them.
  Rationale: less dense is easier on the eyes/brain, less strain mean lower likelihood of bugs.
  ```js
  // bad
  1+2/3
  1*(2/3)
  if (i=4)

  // good
  1 + 2 / 3
  1 * (2 / 3)
  if (i = 4)
  ```

* Align grouped variables.
Note that, we don't need to align all the variales, some variables will be of different group or, too long to align. Leave them. Or align them as another `block`
  ```js
  // bad
  let first = 1;
  let firstFirstFirt = 2;
  let second = 3;

  // good
  let first          = 1;
  let firstFirstFirt = 2;
  let second         = 3;
  ```

* Object 
  ```js
  // bad
  let object = {'name', 'address', ....};
  let objectArray = [{'name', 'address', ....}];

  // good
  let object = 
    {
        'name', 
        'address', 
        ....
    };
  let objectArray = [
      {
          'name', 
          'address', 
          ....
      }
  ];
  ```

* Unary minus does not require a space after it. => i.e. `-5` is okay, `- 5` not

* Avoid using ternary operator if the condition is not easy to understand.

## Ternary Operator for JSX
* Try to divide things and store them into variables. Then add them in appropriate places.
  ```js
  // Not recommended
  return (
    <div>
        <InfoForm>
            ....
            ....
        </InfoForm>
        <Address>
            ....
            ....
        </Address>
    </div>
  );

  // Better
  let addressBlock = (
    <Address>
        ....
        ....
    </Address>
  );
  let infoFormBlock = (
    <InfoForm>
        ....
        ....
    </InfoForm>
  );
  return (
    <div>
        {infoFormBlock}
        {addressBlock}
    </div>
  );
   ```
   
* Now let's say, we have a condition (`ternary`) in a variable. Follow format of `ternary operator` and `JSX`
  ```js
  let addressBlock = isAddressInAPI 
    ? (
        <Address>
            ....
            ....
        </Address>
    ) 
    : null;
  let infoFormBlock = isInfoNeeded
    ? (
        <InfoForm>
            ....
            ....
        </InfoForm>
    )
    : (
        <Hudai>
            ....
        </Hudai>
    )
  return (
    <div>
        {infoFormBlock}
        {addressBlock}
    </div>
  );
   ```
* Try to group variables within brackets. Not mandatory always.
  ```js
  // Not recommended
  return x + y

  // Better
  return (x + y)
   ```
   

* Break down function parameter as it looks better
  ```js
  // bad
  let maxValue = max(someValueOne, someValueTwo, someValueThree, someValueFour, someValueFive, someValueSix);

  // good
  let maxValue = max(someValueOne, someValueTwo, someValueThree, 
                    someValueFour, someValueFive, someValueSix);
  ```

## Alignment
* Will be updated later

## Casing
* Class name should be PascalCased
  ```js
  // Good
  class DemoClass {
    // .... 
  }
  ```
* Function/Method name should be camelCased
  ```js
  // Good
  function myFunction () {
    // .... 
  }
  ```
* Variable name should be snake_cased or camelCased.
  ```js
  // Good
  int total_members = 270;
  int totalStudents = 100; // preferrable for JS
  ```

## Naming
* Please note: 
**A descriptive name is way better than comments.** 
In fact you should avoid comments as much as you can. You variable, function, class name should self descriptive.
* In general, avoid single letter variable names. But sometimes it's okay to use these in loops
  ```js
  for (e in elements) { // Still, element makes more sense, but it's okay
      ...
  }
  for (p in products) {// Still, product makes more sense, but it's okay
      .. 
  }
  ```
* Do not use leading underscore while naming variables if possible. Let's say, we have `data` and another copy of it is needed.
  ```js
  let data  = [...something..];
  let _data = [..modify `data` and store it here]
  // If we can't a better name, at least updatedData or responseData (if we get it from API) would be better. 
  // Better ways
  let updatedeData = [..modify `data` and store it here];
  // OR 
  let responseData = [..modify `data` and store it here];
  ```
* Avoid using prepositions in names. Typically there is an alternative with better readability.
  ```js
  // bad
  let numberOfItems
  let keyForSomething

  // good
  let itemCount
  let somethingKey
  ```
* Class name should be a noun or noun phrase.
  ```js
  class Student {
     // .... 
  }
  ```
* Function/Method name should be a verb or verb phrase. 
  `getTotalSum ();`
* Pick one word per concept
  Avoid using different but similar words to define the same concepts. For instance, don’t use `fetch`, `get` and `retrieve` 
 in the same project for the same responsibility.
* Use pronounceable names.
* Make meaningful distinctions
  Don’t use names with similar meanings. For instance, `product_data` and `product_info` do not have a proper distinction. Just by looking at the name, you can't assume the intentions of these two variables. These are called noise words. Some of the other noise words are `a`, `an`, and `the`.

## Brackets
* Try to group variables within brackets. Not mandatory always.
  ```js
  // Not recommended
  return x + y

  // Better
  return (x + y)
   ```

