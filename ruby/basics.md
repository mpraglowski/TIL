# The bacics of Ruby

## 2015-01-27

### Nested Exceptions in Ruby 2.1.0

With Ruby 2.1.0, one can easily trace the original exception.
http://www.ploughthroughruby.co.uk/2014/01/06/nested-exception-in-ruby-2.1.0.html/

```ruby
def some_method
  do_sth_that_cause_error
rescue => e
  raise StandardError
end

begin
  some_method
rescue => e
  puts e.message
  nested_error = e.cause
  #... here you could access details of nested error
end
```
