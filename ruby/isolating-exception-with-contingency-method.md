### Isolating exception policy with a Contigency Method

*Taken from Exceptional Ruby*


One way to refactor begin-heavy code towards this ideal of a single rescue
clause per method is to make use of a contingency method. A contingency
method cleanly separates business logic from failure handling. It is helpful
in code which repeatedly has to cope with the possibility of a particular
class of failure.
Let’s say we have a codebase which makes numerous calls which might
raise an IOError:


    begin
      something_that_might_fail
    rescue IOError
      # handle IOError
    end

We can refactor the error handling out into a contigency method:

    def with_io_error_handling
      yield
    rescue
      # handle IOError
    end

    with_io_error_handling { something_that_might_fail }

The policy for IOError handling has been moved to a single location. And we can re-use this contingency method to clean up other sections of code.

