# Fresh Crypto Lib (FCL) : solidity


## Content

### FCL_elliptic.sol: 
Optimized Implementation of the ECDSA P256 using XYZZ coordinates.

Gas cost of ecdsa verification (with 100000 runs in configuration files):
- 200K without precomputation table
- 75K with precomputations table of 16kb

Full test with WychProof vectors and comparizon to existing libraries (orbs-network, obvioustech) is available in tests/WebAuthn_forge.



### FCL_eddsa.sol: 

Unfinished optimized implementation of EDDSA over ed25519 as specified by RFC 8032 https://datatracker.ietf.org/doc/html/rfc8032.
Gas cost: 270K, (compared to best of our knowledge here at 1.2M: https://github.com/javgh/ed25519-solidity

ToDO: implement same hack as for secp256r1

### FCL_Webauthn:
implementation of WebAuthn authentication mechanism on top of P256/sec256r1 ecdsa

 
gas cost of WebAuthn verification (to be check again in forge):

- 257K without precomputations,
- 137K with precomputations (16kb, using FCL_ecdsa_precompute.sage).


### Testing:
see directory tests/Webauthn_forge 