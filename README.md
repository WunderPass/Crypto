
	                                                
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


Your WunderPass keys never leave your browser.
The encryption is done within it. That is called client side encryption.

We use crypto-js as the base encryption library to handle this. 

https://cryptojs.gitbook.io/docs/

Our Vision is that assymetric cryptography can replace the ID management Systems 
nowadays.

Having an identity is thus replaced by having a private key.
This private key is crucial to "your" WunderPass.

Also we want password-less logins. That means, your private key is stored in your
browsers local storage. To keep these stored private keys safe, they get stored
encrypted with crypto-js. Encrypted with crypto-js and your Password.
 
When it comes to signing, that means to authenticate or to make a transaction, 
you need to type in the password to temporarily unlock the encrypted private 
key in your local storage. 

Integrated in the blockchain universe, the libraries ethereumjs-wallet and bip39 
are being used as well. 
With hdkey from ethereumjs-wallet and bip39, the restoring process of a lost private 
key based on the mnemonic is achieved. 

The other user data, that means 
* the csrf token
* and the wunderID (username)
 
are held in your browsers local storage, unencrypted.

To get your balances, your browser communicates directly with the blockchain.

This information is public on the blockchain anyway.
