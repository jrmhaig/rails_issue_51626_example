# Minimal example for https://github.com/rails/rails/issues/51626

This example shows a 'stack trace too deep' error due to the following combination:

* Rails 7.1.
* [`logstasher`](https://rubygems.org/gems/logstasher) used for writing logs and set to log at the debug level. This results in details of particals, including their `locals`, to be logged as JSON.
* A form builder instance being passed to a partial via `locals`.

The `rails_7_0` branch contains the same example with Rails 7.0 where the page can be viewed without error.