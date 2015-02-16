Olafur Gudmudnsson olafur@cloudflare.com 2014/12/01 
A simple program to check what DNSSEC algorithms a particular resolver
validates. 
This program is written in Go and it is the first program I wrote, it
uses go routines to perform the cheks in parallel. 
Some resolvers return lots of timeouts when this program runs against
them, just rerun the program to and the resolvers give better
results. 

This program requires the package miekg/dns which can be added by issuing 
     "go get github.com/miekg/dns"

USage:  
This program has argressive timeouts to make sure it runs fast. 
If you get lots of timeouts run the program again against the same server to see 
if is slow in validation. 

Command line arguments: ./alg_rep: [-r resolver] [-d] [-v] 
  -d=false: All debug on
  -r="8.8.8.8": address host or host:port of DNS resolver
  -v=false: Short output

  -r selects the resolver to check, 
  Setting the -d option will give lots more output 
  -d should only be used when checking strange results as the output is excessive and 
     only for experts to interpret. 


