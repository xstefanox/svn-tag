svn-tag
=======

A shell script to ease and automate the process of releasing software versioned under a Subversion repository.

The release is performed from the current trunk of the repository and ensures that the selected tag follows the semantic versioning. The tags are created 'as it should be': the correct version control ancestry is created between each version and trunk, so that `svn switch` will actually work.

#### Requirements

The repository must follow the standard svn layout, having the following directories:

    /myrepo
      /trunk
      /branches
      /tags

#### Example

    svn-tag 1.2.3
    
This command executes the following operations:

1. create the directory `/tags/1.2.3`
2. recursively copy everything from `/trunk` to `/tags/1.2.3`
3. Commit the modifications
