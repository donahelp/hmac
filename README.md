# hmac

Validate HMAC in Golang.

## Who uses it HMAC?

[GitHub](https://developer.github.com/webhooks/securing/), Patreon and some other parties will use HMAC signing with their outgoing webhooks so that you can verify the webhook is from the expected sender.

## How it works:

HMAC uses a symmetric key that both sender/receiver share ahead of time. The sender will generate a hash when wanting to transmit a message - this data is sent along with the payload. The recipient will then sign payload with the shared key and if the hash matches then the payload is assumed to be from the sender.

[Read more on Wikipedia](https://en.wikipedia.org/wiki/HMAC)

# Documentation

NOTE: The link below is no longer valid. TODO: create DonaHelp godoc for hmac
[![](https://godoc.org/github.com/alexellis/hmac?status.svg)](http://godoc.org/github.com/alexellis/hmac)

## Example:

```
import hmac "github.com/donahelp/hmac/v2"

...
var input []byte
var signature string
var secret string

valid := hmac.Validate(input, signature, secret)

fmt.Printf("Valid HMAC? %t\n")
```
