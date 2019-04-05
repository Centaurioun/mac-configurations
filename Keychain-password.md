- Ref: https://www.netmeister.org/blog/keychain-passwords.html

  #### Using the OS X Keychain to store and retrieve passwords

  ##### Adding secrete to toolchain

  - By using GUI ("Keychain-Access")

    1. Select File->New Password Item (cmd+N)
    2. Make sure Keychain item name is distinct —> `service-name` in command line
    3. Account name —> `USER` in command line, it is $whoami, or echo ${USER}

  - Command line using security command

    - Add command: add-generic-password `security add-generic-password -h`
      `$ security add-generic-password -a ${USER} -s <service-name> -w `

      Enter password on prompt, 

    - Update password if already exists : `-U ` flag

      `$ security add-generic-password -a ${USER} -s <service-name> -w -U`

    - Delete password: `security delete-generic-password -h`

      `security delete-generic-password -a ${USER} -s <service-name>`

    - Retrieve Password: `security find-generic-password -h`

      
