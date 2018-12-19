# Development and Code Review Cheat Sheet

- [Documentation](#Documentation)
- [Performance](#performance)
- [OOAD](#ooad)
- [Reusability](#reusability)
- [Thread safety](#thread-safety)
- [Error Handling](#error-handling)
- [Testing(Unit and Dev)](#testing-unit-and-dev)

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
