# nagios-plugins-sitemon
Bash script to poll CERN Sitemon and send results to Nagios/Icinga

Credit: Borja Garrido (CERN) | Jordi Casals (PIC)

## Requirements
### jq
jq is a lightweight and flexible command-line JSON processor --> https://stedolan.github.io/jq/

### Monit API key
You need to generate yours with monit Grafana or ask to CERN monit team for one.

## Usage
Single Flavour

```
./check_sitemon -a <api_key> -v <vo> -p <profile> -s <site> -f <flavour>
```

You can see an example of the output here:
```
[root@jcasals01 nagios-plugins-sitemon]# ./check_sitemon -a $API_KEY -v cms -p CMS_CRITICAL -s T1_ES_PIC -f HTCONDOR-CE
HTCONDOR-CE: All hosts OK!

HOSTS
=====
ce13.pic.es: OK
ce14.pic.es: OK
```

*NOTE: Multiple flavors at once will be evaluated in the future*

### PIC Argument Examples
```
vo      | atlas                 | cms                   | lhcb
profile | ATLAS_CRITICAL        | CMS_CRITICAL_FULL     | LHCB_CRITICAL
site    | pic                   | T1_ES_PIC             | LCG.PIC.es
-----------------------------------------------------------------------
flavour | CREAM-CE | HTCONDOR-CE | SRM (atlas, cms)
```
