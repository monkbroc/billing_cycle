# Billing Cycle

[![Build Status](https://travis-ci.org/simplymadeapps/billing_cycle.svg?branch=master)](https://travis-ci.org/simplymadeapps/billing_cycle)
[![Code Climate](https://codeclimate.com/github/simplymadeapps/billing_cycle/badges/gpa.svg)](https://codeclimate.com/github/simplymadeapps/billing_cycle)
[![Test Coverage](https://codeclimate.com/github/simplymadeapps/billing_cycle/badges/coverage.svg)](https://codeclimate.com/github/simplymadeapps/billing_cycle/coverage)
[![Yard Docs](http://img.shields.io/badge/yard-docs-blue.svg)](http://www.rubydoc.info/github/simplymadeapps/billing_cycle/)

Billing Cycle is a gem used to calculate the next billing date for a recurring subscription.

## Installation

Add this line to your application's Gemfile:

```ruby
gem "billing_cycle"
```

And then execute:

```bash
$ bundle
```

## Usage

```ruby
original_billing_date = Time.zone.parse("2018-01-31 00:00:00")
billing_interval = 1.month
billing_cycle = BillingCycle::BillingCycle.new(original_billing_date, billing_interval)

Time.zone.now
# => Tue, 26 Jun 2018 00:00:00 CDT -05:00

billing_cycle.next_due_at
# => Sat, 30 Jun 2018 00:00:00 CDT -05:00

billing_cycle.next_due_at(Time.zone.parse("2020-02-01 00:00:00")
# => Sat, 29 Feb 2020 00:00:00 CST -06:00

billing_cycle.previous_due_at
# => Thu, 31 May 2018 00:00:00 CDT -05:00

billing_cycle.previous_due_at(Time.zone.parse("2020-02-01 00:00:00")
# => Fri, 31 Jan 2020 00:00:00 CST -06:00
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License
The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
