#### DESCRIPTION
This python script compare tls cipher suites of a server to baselines.

Cipher suites are retrieved with the testssl.sh shell script.


#### GUIDE 
To launch the script :

```sh
 test.py sslcompare.py -u <url or ip> -b <baselinefile>
   -u : [MANDATORY] url or ip of the target
   -b : baseline file (json format). Default : anssi.json
```
   
Examples :
```sh
   test.py sslcompare.py -u mytargetsite.com 
   test.py sslcompare.py -u mytargetsite.com -b mybaseline.json
```
#### Baseline files :

Baseline are formated as json files.
Baseline files are stored in the baseline directory
Default baseline file is anssi.json (ANSSI recommendations)
For each tsl version suite can be either :
- recommended
- degraded
- last hope (suites that can be used as a last resort)
- depreciated

To add a baseline, create a file and fill it the same way
anssi.json is filled.
The pass your baseline file in the command line :
```sh
test.py sslcompare.py -u mytargetsite.com -b mybaseline.json
```

   
# NOTES 

TLS 1 is equivalent to TLS 1.1