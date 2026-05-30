# TestDrive Project - CodeIgniter 4 Unit Testing Activity

A hands-on unit testing activity for CodeIgniter 4 demonstrating PHPUnit test implementation for verifying homepage HTTP status.

---

## Activity Objective

Write a unit test that verifies the homepage returns HTTP 200 (OK) status code.

---

## Test Results

    PHPUnit 10.5.63 by Sebastian Bergmann and contributors.

    .                                                                    1 / 1 (100%)

    Time: 00:00.034, Memory: 10.00 MB

    OK (1 test, 1 assertion)

### Test Summary

| Metric     | Result |
|------------|--------|
| Tests Ran  | 1      |
| Assertions | 1      |
| Passed     | Yes    |
| Failures   | 0      |
| Errors     | 0      |

---

## Technologies Used

- PHP 8.5.3  
- CodeIgniter 4 - PHP Framework  
- PHPUnit 10.5.63 - Testing Framework  
- Composer - Dependency Manager  
- XAMPP - Local Development Environment  

---

## Project Structure

    testdrive-project/
    ├── app/
    │   └── Controllers/
    │       └── Home.php
    ├── tests/
    │   └── app/
    │       └── Controllers/
    │           └── HomeTest.php
    ├── vendor/
    ├── .env
    ├── phpunit.dist.xml
    └── spark

---

## The Test Code

### Test File Location

    tests/app/Controllers/HomeTest.php

### Test Code

    <?php

    namespace App\Tests\Controllers;

    use CodeIgniter\Test\CIUnitTestCase;
    use CodeIgniter\Test\FeatureTestTrait;

    class HomeTest extends CIUnitTestCase
    {
        use FeatureTestTrait;

        public function testHomePage()
        {
            $result = $this->get('/');
            $result->assertStatus(200);
        }
    }

### What This Test Does

| Line              | Purpose                                       |
|-------------------|-----------------------------------------------|
| $this->get('/')   | Simulates an HTTP GET request to homepage     |
| assertStatus(200) | Verifies the response status code is 200 OK   |

---

## How to Run the Test

### Prerequisites

- PHP 7.4+ installed  
- Composer installed  
- XAMPP or any local server  

### Setup Instructions

1. Clone the repository  
       git clone <your-repo-url>  
       cd testdrive-project  

2. Install dependencies  
       composer install  

3. Set up environment  
       cp env .env  

4. Start the development server (in one terminal)  
       php spark serve  

5. Run the test (in another terminal)  
       vendor/bin/phpunit tests/app/Controllers/HomeTest.php  

### Alternative Test Commands

Run with readable output:  
       vendor/bin/phpunit tests/app/Controllers/HomeTest.php --testdox  

Run all tests:  
       vendor/bin/phpunit  

Run with detailed information:  
       vendor/bin/phpunit --verbose  

---

## Expected Output

    PHPUnit 10.5.63 by Sebastian Bergmann and contributors.

    .                                                                    1 / 1 (100%)

    Time: 00:00.034, Memory: 10.00 MB

    OK (1 test, 1 assertion)

### Output Legend

| Symbol | Meaning         |
|--------|-----------------|
| .      | Test passed     |
| F      | Test failed     |
| E      | Test error      |
| I      | Incomplete test |

---

## Learning Outcomes

By completing this activity, I learned:

- What unit testing is and its purpose  
- How to write test functions using PHPUnit  
- How to use assertions to verify behavior  
- How to analyze stack traces and CI4 errors  
- How to execute tests from the command line  

---

## Code Explanation

### The Test Class

    class HomeTest extends CIUnitTestCase

Extends CodeIgniter 4 base test case class and inherits testing functionality.

### The Test Trait

    use FeatureTestTrait;

Enables HTTP request simulation and provides methods like get(), post(), put(), and delete().

### The Test Method

    public function testHomePage()

The method name must start with "test" and contains the actual test logic.

### The Assertion

    $result = $this->get('/');
    $result->assertStatus(200);

- get('/') simulates visiting the homepage  
- assertStatus(200) checks for HTTP 200 response  

---

## Notes

The warning "No code coverage driver available" is informational only. It does not affect test execution or results. To remove the warning, install or enable Xdebug with coverage mode.

---

## References

- https://phpunit.de/documentation  
- https://codeigniter.com/user_guide/testing/index.html  
- https://codeigniter.com/user_guide/testing/overview.html  

---

## Author

Advanced Web Development - Week 14 Activity  
The Test Drive - Unit Testing and Debugging  

---

## Date

2026  

---

## Activity Completion Status

Activity: The Test Drive - COMPLETED  

- Test file created correctly  
- Test method implemented properly  
- Assertion verifies HTTP 200 status  
- Test runs successfully from command line  

Status: PASSED
