
A class to manipulate arrays in efficient ways to solve real world problems.

## Requirement

1.  PHP 7.2 or grater.
2.  Composer.

## Installation

Installing this package is very simple, first ensure you have the right PHP version and composer installed then in your terminal/(command prompt) run:
  `composer require lablnet/arrays`

## Features

 1. Determine whether the given dataSet is really array?
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $arr = array(2, 2, 3, 4, 4, 4, 4, 8, 8, 6, 6, 9, 9, 9, 9); 
        var_dump(Arrays::isReallyArray($arr)); //True
        var_dump(Arrays::isReallyArray([]));   //False
        ```
 2. Determine the given array is (sequential)indexes.?
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $arr = array(2, 2, 3, 4, 4, 4, 4, 8, 8, 6, 6, 9, 9, 9, 9); 
        var_dump(Arrays::isSequential($arr)); //True
        var_dump(Arrays::isSequential(['a' => 1]));   //False
        ```

 3. Determine the given array is assoc.?
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $arr = array(2, 2, 3, 4, 4, 4, 4, 8, 8, 6, 6, 9, 9, 9, 9); 
        var_dump(Arrays::isAssoc($arr)); //False
        var_dump(Arrays::isAssoc(['a' => 1]));   //True
        ```

 4. Determine the given array is multi-dimensional.?
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $arr = array(2, 2, 3, 4, 4, 4, 4, 8, 8, 6, 6, 9, 9, 9, 9); 
        var_dump(Arrays::isMulti($arr)); //False
        var_dump(Arrays::isMulti(['a' => ['b' => 'c']]));   //True
        ```

 5. Get the type of array.
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $arr = array(2, 2, 3, 4, 4, 4, 4, 8, 8, 6, 6, 9, 9, 9, 9); 
        var_dump(Arrays::getType($arr)); //indexes
        var_dump(Arrays::getType(['a' => ['b' => 'c']]));   //multi
        ```

  6. Add an element to an array using "operation" notation if it doesn't exist.
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        var_dump(Arrays::add(['name' => 'desk', 'price' => null], 'price', 100)); // ['name' => 'desk', 'price' => 100]
        ```

 7. Set an array item to a given value using "operator" notation.
      - Example:   
      - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['products' => ['desk' => ['price' => 100]]];
		Arrays::set($array, 'products.desk.price', 200, '.');
		// ['products' => ['desk' => ['price' => 200]]]
        ```

8. Get an item from an array using "operator" notation(The `Arrays::get` method retrieves a value from a deeply nested array using "dot" notation:).
    - Example:   
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['products' => ['desk' => ['price' => 100]]];
		$price = Arrays::get($array, 'products.desk.price', '.');
		// 100
        ``` 
  The `Arrays::get` method also accepts a default value, which will be returned if the specific key is not found.

 9. Determine if an item or items exist in an array using 'Operator' notation.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['product' => ['name' => 'Desk', 'price' => 100]];
		$contains = Arrays::has($array, 'product.name', '.');
		// true
		$contains = Arrays::has($array, ['product.price', 'product.discount'], '.');
		// false
       ``` 


 10. Determine if an item or items exist in an array using 'Operator' notation.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['product' => ['name' => 'Desk', 'price' => 100]];
        $assoc = Arrays::multiToAssoc($array);
        // ['name' => 'Desk', 'price' => 100]
       ``` 

 11. Converted a multi-dimensional associative array with `dot`.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['products' => ['desk' => ['price' => 100]]];
		$dot= Arrays::dot($array);
		// ['products.desk.price' => 100]
       ``` 

 12. Converted a multi-dimensional associative array with `operator`.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['products' => ['desk' => ['price' => 100]]];
		$dot = Arrays::multiToAssocWithSpecificOpr($array);
		// ['products.desk.price' => 100]
       ``` 

 13. Push an item onto the beginning of an array.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['red', 'green', 'blue'];
        $prepend = Arrays::prepend($array, 'yellow');
        // ['yellow', 'red', 'green', 'blue'];
       ``` 

 14. Push an item to the end of array.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['red', 'green', 'blue'];
        $append = Arrays::append($array, 'yellow');
        // ['red', 'green', 'blue', 'yellow'];
       ``` 

 15. Get the unique elements from arrays.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['red', 'green', 'blue', 'red'];
        $unique = Arrays::append($array);
        // ['red', green', 'blue'];
       ``` 

 16. Get a subset of the items from the given array.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array =  [
            'users' => 
            [
                'id' => 1,
                'name' => "Alex",
                'username' => 'peter',
            ],
            [
                'id' => 2,
                'name' => "Peter Khot",
                'username' => 'peter',
            ],
            [
                'id' => 3,
                'name' => "John",
                'username' => 'test',
            ]
        ];
        $subSetOfArray = Arrays::subSetOfArray($array, 'name');
        // [];
       ``` 

 17. Remove one or many array items from a given array using "operator" notation.
    - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['products' => ['desk' => ['price' => 100]]];
		Arrays::forget($array, 'products.desk');
		// ['products' => []]
    ```

 18. Get all of the given array except for a specified array of keys.
   - Example:
    - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['name' => 'Desk', 'price' => 100]
		$filtered = Arrays::except($array, ['price']);
		// ['name' => 'Desk']
		```

 19. Get a value from the array, and remove it.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
		$array = ['name' => 'Desk', 'price' => 100];
		$name = Arrays::pull($array, 'name');
		// $array: ['price' => 100]
		```

 20. Changes the case of all keys in an array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['name' => 'Desk', 'price' => 100];
        $name = Arrays::arrayChangeCaseKey($array, CASE_UPPER);
        // ['NAME' => 'Desk', 'PRICE' => 100]
        ```
  
 21. Changes the case of all values in an array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['name' => 'Alex'];
        $name = Arrays::arrayChangeCaseValue($array, CASE_UPPER);
        // ['name' => 'ALEX']
        ```

 22. Remove duplicate values from array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ````
        $name = Arrays::removeDuplicates($array);
        // $array: ['red', 'green', 'blue']
        ```


23. Get the most occurring value from array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['red', 'blue', 'green', 'red', 'blue'];
        $name = Arrays::mostOccurring($array);
        // ['red', 'blue']
        ```

24. Get the least occurring value from array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['red', 'blue', 'green', 'red', 'blue'];
        $name = Arrays::leastOccurring($array);
        // ['green']
        ```

25. Convert the array into a query string.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = [
            'foo' => 'bar',
            'baz' => 'boom',
            'cow' => 'milk',
            'php' => 'hypertext processor'
        ];
        $name = Arrays::query($array);
        // foo=bar&baz=boom&cow=milk&php=hypertext+processor
        ```


26. Filter the array using the given callback (THIS METION WILL NOT WORKS WITH MULTIDIMESSIONAL ARRAY.).
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = [100, '200', 300, '400', 500];
        $array = Arrays::where($array, function ($value, $key) {
            return is_string($value);
        });
        // [1 => '200', 3 => '400']
        ```

27. Get one or a specified number of random values from an array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = ['red', 'green', 'blue'];
        $name = Arrays::random($array);
        // ['blue'];
        ```

 28. Get multiple values of same keys from multi-dimessional array.
     - Example:
     - ```php
        use Lablnet\Arrays;
        require '../vendor/autoload.php';
        $array = [
            ['developer' => ['id' => 1, 'name' => 'Alex']],
            ['developer' => ['id' => 2, 'name' => 'Peter']],
        ];
        $name = Arrays::pluck($array, 'name');
        // ['Alex', 'Peter'];
        ```