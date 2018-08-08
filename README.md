# Bitfi-PoC
Proof of concept for Bitfi website attacks

# What attacks?

The Bitfi website is vulnerable to a few attacks;

  - ~~XSS~~ [FIXED]
  - ~~SQLi~~ [FIXED]
  - ~~Email injection~~ [FIXED]

# Initial Report

The initial report was sent via email to Bitfi support team on 08/07/2018. If there is no response or no fix by 08/13/2018 I will release PoC code for the attacks publically.


# Patches 

The PoC for each vulnerability was patched some time between the report and now.

# PoC images

Once you have requested an order for how many wallets you want, you are taken to a form that ask for your information:

![poc-bitfi-1](https://user-images.githubusercontent.com/14183473/43848476-a335acac-9af8-11e8-9aed-6d15862253e0.png "#staysalty")

In this form, the email validation aspect _allowed_ any sort of input to be placed inside of the form:

![poc-bitfi-2](https://user-images.githubusercontent.com/14183473/43848477-a35864c2-9af8-11e8-82a5-d54427904f43.png "#staysalty")

From here, the form _use_ to render the validation during initialization of the payment (_depending on the payload you can lose money_) which in turn would cause the scripts, and SQL queries to execute, here is an image of the above script rendered:

![script-rendered](https://user-images.githubusercontent.com/14183473/43849055-2121b48e-9afa-11e8-97bd-4dfec778edd3.png "#staysalty")
