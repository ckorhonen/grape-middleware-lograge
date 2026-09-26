# Working on grape-middleware-lograge

`lib/grape/middleware/` contains the middleware and Rails integration;
`lib/lograge/formatters/` contains the formatter. Tests are separated into
`spec/lib/`, `spec/integration/`, and `spec/integration_rails/`.

Use a compatible legacy Ruby/Bundler environment: `.travis.yml` exercises Ruby
2.2–2.3 and Bundler 1.10.5, and the gemspec constrains Grape below 1. Install with
`bundle install`; do not upgrade dependencies merely to suit the host.
`bundle exec rake spec`, `bundle exec rake integration`, and
`bundle exec rake integration_rails` select the suites; `bundle exec rake` runs
all three. There is no separate lint or typecheck task.

Preserve parameter filtering and error-response logging. A Rails-specific change
needs the Rails suite; middleware changes need the relevant integration coverage.

## Completing changes

Follow existing patterns and carry authorized work through the relevant checks,
repairing failures caused by the change. Choose routine implementation details
directly; ask only when missing information materially changes scope or outcome.
For documentation-only edits, check the diff, referenced paths, and command
accuracy rather than starting application runtimes. If a prerequisite blocks a
check, report the exact blocker and continue independent authorized work. Close
with changed paths, checks actually run and results, and remaining unverified
behavior; distinguish commands inspected from commands executed.
