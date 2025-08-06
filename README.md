# Rails System Tests with Capybara, Selenium & Geckodriver

## Getting Started

### Prerequisites

* Ruby (3.x)
* Rails (7.x)
* Firefox browser (latest)
* Geckodriver installed (brew install geckodriver)
* Chrome browser (optional, see below)
* Chromedriver (optional, for Chrome tests once compatible)

---

### 1. Setup

Clone the repo:

git clone [https://github.com/pinkopaque22/rails-system-tests-capybara-selenium.git](https://github.com/pinkopaque22/rails-system-tests-capybara-selenium.git)
cd rails-system-tests-capybara-selenium

Install dependencies:

bundle install

Set up the database:

rails db\:create db\:migrate db\:seed

---

## Running System Tests

### Using Firefox (Geckodriver)

This is the default setup and works on macOS without version mismatch issues:

BROWSER=firefox rails test\:system

### Using Chrome (Chromedriver)

Once the Chrome/Chromedriver version mismatch is resolved (or if you install a compatible Chrome version), update application\_system\_test\_case.rb to use Chrome:

driven\_by \:selenium, using: \:headless\_chrome, screen\_size: \[1400, 1400]

Then run:

BROWSER=chrome rails test\:system

**Note:** If you run into Chromedriver download or compatibility errors, please switch back to Firefox or wait for matching releases.
