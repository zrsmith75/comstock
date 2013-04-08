Comstock
========

**Disclaimer**: Use at your own risk.  I have not tested this using real money, and I don't want you to lose money!  I plan on using this personally, and I wanted to get the code out there since there aren't many similar projects on Github.  

Thanks, 
Ryan

The Future of Buying Bitcoin (for me, anyway)
--------

Since the price of bitcoin will never fall, ever, I'm using a very basic
long strategy of buying when the price dips.  I'd encourage you to use this at your
own risk, as it's in no way stable (yet).  

I like the idea of passively buying bitcoin because I'm extremely bullish on its
future, and I just started playing with the [Bitfloor API](https://bitfloor.com/docs/api).  
Eventually, I'd like to incorporate historical data and use a more sophisticated strategy.

How Do I Install This Thing?
--------

I have the bot using the test API, but to change over to trading real money (AT YOUR OWN RISK),
you must change the **host** in **keys.json** from:

    "https://api.testnet.bitfloor.com"

to:

    "https://api.bitfloor.com"

I'm using **redis** as a datastore, so you'll need to install that:

    brew install redis

Next, I'm using the wonderful **HTTParty** gem for pulling data from the REST API:

    gem install httparty

Signing requests is a key to the security of the API, but it's kind of a pain.  I used the
**querystring** gem to make signing requests simple.  Install the gem as well using:

    gem install querystring

Run the command **redis-server** in a separate terminal tab to start redis

Lastly, create a **keys.json** file form **keys_example.json**.  Update **keys.json** to use your own API key / secret / passphrase (ports must be 443 for https)

How Do I Use This Thing?
---------

Once you've cloned the repo and updated the keys.json with your relevant information and you have Redis
running, type the following:

    ruby comstock.rb

You'll be prompted to either use the defaults or choose your own. I tried to make sensible defaults based on the amount of $ and BTC the user has in his/her account, but you can override them at your own risk by entering 'N' at the first prompt.  Good luck, and remember that this has only been run using the test API.  It is in no way ready for real money trading use (yet).

Contribute
---------

Pull requests are more than welcome, as usual:

1. Fork this repo

2. Create a branch with excellent code (`git checkout -b excellence`)

3. Commit the new code, push to your forked repo (`git push origin excellence`)

4. Create a pull request, and I promise I'll look at it

