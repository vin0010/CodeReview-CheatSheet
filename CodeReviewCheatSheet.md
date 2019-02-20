# Development and Code Review Cheat Sheet
>I believe there are 7 aspects in development and code review that will save lot of time and cost in software engineering. 

- [Documentation](#documentation)
- [Performance](#performance)
- [OOAD](#ooad)
- [Reusability](#reusability)
- [Thread safety](#thread-safety)
- [Error Handling](#error-handling)
- [Testing](#testing)

## Documentation
- Code should be self explanatory. Get a feel of story reading, while going through the code. Use appropriate name for variables, functions and classes. If you are taking more time to understand the code, then either code needs refactoring or at least comments have to be written to make it clear.
- Clearly document whet happens with all edge cases.
- Complex algorithms are explained and justified.
- Code that depends on behavior in external libraries is documented with reference to external documentation. if planning to use new/existing libraries we need to understand code behavior completely and document it out.
- Document all test cases that need to be dev tested as part for development process.

## Performance
- Objects are duplicated only when necessary. Document the explicit use case with details.
- No busy-wait loops instead of proper thread synchronization methods.
- Memory usage should be acceptable even for large inputs.
- Use data type that bets suits the needs such as String Builder Generic collection classes etc.
- Leverage Lazy loading, asynchronous and parallel processing as much as possible

## OOAD
- Do not place more than one responsibility into a single class or function(if so refactor into separate classes and functions). There should be a limit for number of lines in a class(typically it should be around 300 to 400).
- Do not create lengthy interfaces, instead split them into smaller interfaces and based on functionality. The interface should not contain any dependencies, which are not required for the expected functionality.  
- Controllers/Services should not have parameter-less constructors, Use proper libraries for dependency injection.
- Old/replaced code should be removed instead of commented out unless there is a specific and documented reason why it is left in place.
- If any new libraries are added, please follow the steps
    - Check about license with legal team
    - Check its security in the community
    - Is the package has permissible level of known issues(one way is to look into its defect backlog and squash rate)?
    - Is the package actively developed or contributed?
    - Stable version of package instead of going for beta version.

## Reusability
- DRY(Do not repeat yourself) principle. The same code should not be repeated more than twice. 
- Consider reusable services, wrappers, functions and components. 

## Thread safety
- Global variables are protected by locks or any stable locking mechanism.
- Objects accessed by multiple threads are accessed only through a lock.
- Locks should be accessed and released in the right order to prevent deadlocks(even in error handling code).

## Error handling
- Handle 
    - Invalid arguments
    - Cover common exceptions i.e Array index out of bound, null checks etc.
- Memory is released and resources are closed under both error and non error conditions.

## Testing
- All new code should have test coverage. Even though it may not be 100% covered but effort should be made to think about the happy path and common error conditions. 
- The code should be easy to test. Refactor into a separate function(if required). Use interfaces while talking to other layers, as interfaces can be mocked easily. Try to avoid static functions and singleton classes as these are not easily testable by mocks.
- Defect fix should have test cases that explicitly recreate the error. Exception could be during time sensitive fix (hotfix or during regression) with a follow up ticket created for refactoring in a subsequent sprints.
- Unit test cover errors and invalid parameter cases.
- Unit tests demonstrate the algorithm is performing as documented.

## For Code reviewers
>in progress
