# Keycard CLI examples

## Requirements

### For linux

Install `pcscd` and run it:

`sudo pcscd -f`

## Commands

### Info

`keycard info -l debug`

### Install

`keycard install -l debug -a _assets/keycard_v3.0.2.cap`

You can force deleting and re-installing the applet passinf the `-f` flag.

### Init

`keycard init -l debug`

### Delete applet and keys

`keycard-cli delete -l debug`

### Shell

```
keycard shell <<END
  keycard-select
  keycard-set-secrets 123456 123456789012 KeycardTest
  keycard-pair
  keycard-open-secure-channel
  keycard-verify-pin {{ session_pin }}
  keycard-derive-key m/44'/60'/0'/0/0
  keycard-sign-message Hello World
  keycard-unpair {{ session_pairing_index }}
END
```
