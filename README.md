# cyber_automate
The aim of this project is to develop a demo merging the following concepts:

- Testing
- Cybersecurity

## Tools Involved

- Code editor: VSCode
- Code host: Github
- Security added
    - git-crypt
    - Dependabot
    - CodeQL Analysis
    - Restricted PRs
    - Github Actions + secrets
- Test development: Toolium - https://github.com/Telefonica/toolium
- SUT: Portswigger Labs - https://portswigger.net/


## Initial configuration

1. Replace `test/conf/properties.cfg` file with `test/conf/clean-properties.cfg`
2. Create a Porswigger account to access the labs
3. Add your credentials to `properties.cfg` file:
    ```text
    [Test]
    url: https://portswigger.net
    username: <USER>
    password: <PASSWORD>
    xss_lab_1: web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded
    sqli_lab_1: web-security/sql-injection/lab-retrieve-hidden-data
    ```

## Test Execution

1. Create virtualenv and install requirements:
    ```bash
    $ virtualenv venv 
    $ source venv/bin/activate 
    $ pip install -r requirements.txt
    ```
2. Execute test cases
    ```bash
    $ cd test
    $ behave
    ```

3. Execute security test cases
    ```bash
    $ cd test
    $ behave -t @security
    ``` 
