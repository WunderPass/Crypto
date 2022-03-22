
	                                                
	          _|  _|                        _|      
	  _|_|_|  _|        _|_|    _|_|_|    _|_|_|_|  
	_|        _|  _|  _|_|_|_|  _|    _|    _|      
	_|        _|  _|  _|        _|    _|    _|      
	  _|_|_|  _|  _|    _|_|_|  _|    _|      _|_|  
	                                                
	                                  
	          _|        _|            
	  _|_|_|        _|_|_|    _|_|    
	_|_|      _|  _|    _|  _|_|_|_|  
	    _|_|  _|  _|    _|  _|        
	_|_|_|    _|    _|_|_|    _|_|_|  
	                                  
	                                                            
	                                          _|                
	  _|_|_|  _|  _|_|  _|    _|  _|_|_|    _|_|_|_|    _|_|    
	_|        _|_|      _|    _|  _|    _|    _|      _|    _|  
	_|        _|        _|    _|  _|    _|    _|      _|    _|  
	  _|_|_|  _|          _|_|_|  _|_|_|        _|_|    _|_|    
	                          _|  _|                            
	                      _|_|    _|                          


### The WunderPass WebApp

## Client side encryption

All your WunderPass keys never leave your browser.
The encryption is done within it. That is called client side encryption.

We use crypto-js as the base encryption library to handle this. 

https://cryptojs.gitbook.io/docs/

# The private key

Our Vision is that assymetric cryptography can replace the ID management Systems 
nowadays.

Having an identity is thus replaced by having a private key.
This private key is crucial to "your" WunderPass.

# Password-less authentification

Also we want password-less logins. That means, your private key is stored in your
browsers local storage. To keep these stored private keys safe, they get stored
encrypted with crypto-js. Encrypted with crypto-js and your Password.

# The Dangerous Situation

When it comes to signing, that means to authenticate or to make a transaction, 
you need to type in the password to temporarily unlock the encrypted private 
key in your local storage. 

# Other Data in your local storage

The other user data, that means 
* the csrf token
* the wunderID (username)
* the public key
 
are held in your browsers local storage, unencrypted.

# The files

The described procedures can be looked up in 

    wunderpass-web/web/services/crypto.js


## Blockchain (ethereum) crypto

# Wallet and Mnemonic

Integrated in the blockchain universe, the libraries ethereumjs-wallet and bip39 
are being used as well. 
With hdkey from ethereumjs-wallet and bip39, the restoring process of a lost private 
key based on the mnemonic is achieved. 

# Communication with the WunderPass Contracts on the polygon mainnet

To mint your wunderNFT, your browser communicates directly with the blockchain.
This communication is based on the web3 library in javascript.

https://web3js.readthedocs.io

# The files

You can find the specific code in

    wunderpass-web/web/services/contract.js
