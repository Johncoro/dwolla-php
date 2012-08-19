# dwolla-php: PHP Wrapper for Dwolla's API
=================================================================================

## Version
1.0.0

## Requirements
- [PHP](http://www.php.net/)
- [CURL PHP](http://php.net/manual/en/book.curl.php)
- [JSON PHP](http://php.net/manual/en/book.json.php)

## Installation

Include the dwolla.php in your PHP code

## Usage

    require 'dwolla.php';
    $Dwolla = new DwollaRestClient();
    $Dwolla->setToken('[OAuth Token Goes Here]');

    // Send money to a given Dwolla ID
    $transactionId = $Dwolla->send($pin, '812-734-7288', 1.00);

## Methods

Authentication Methods:

    getAuthUrl()        ==> (string) OAuth permissions page URL
    requestToken($code) ==> (string) a never-expiring OAuth access token
    setToken($token)    ==> (bool) was token saved?
    getToken()          ==> (string) current OAuth token

Users Methods:

    me()                ==> (array) the user entity associated with the token
    getUser($user_id)   ==> (array) the user entity for {$user_id}
    
Register Methods:

    register()
    
Contacts Methods:

    contacts()
    nearbyContacts()
    
Funding Sources Methods:

    fundingSources()
    fundingSource()
    
Balance Methods:

    balance()
    
Transactions Methods:

    send()
    request()
    transaction()
    listings()
    stats()
    
Offsite Gateway Method:

    startGatewaySession()       ==> (bool) did session start?
    addGatewayProduct()         ==> (bool) was product added?
    getGatewayURL()             ==> (string) checkout URL
    verifyGatewaySignature()    ==> (bool) is signature valid?
    
Helper methods

    getError()          ==> (string) error message
    parseDwollaID($id)  ==> (bool) is valid Dwolla ID?
    setMode($mode)      ==> (bool) did mode change?

## Examples

This repo includes various usage examples, including:

* Authenticating with OAuth [oauth.php]
* Sending money [send.php]
* Fetching account information [accountInfo.php]
* Grabbing a user's contacts [contacts.php]
* Listing a user's funding sources [fundingSources.php]
* Creating offsite gateway sessions [offsiteGateway.php]

## Credits

Michael Schonfeld &lt;michael@dwolla.com&gt;

## Support

- Dwolla API &lt;api@dwolla.com&gt;
- Michael Schonfeld &lt;michael@dwolla.com&gt;

## References / Documentation

http://developers.dwolla.com/dev

## License 

(The MIT License)

Copyright (c) 2012 Dwolla &lt;michael@dwolla.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.