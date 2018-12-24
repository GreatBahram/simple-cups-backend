# Simple Cups Backend
Simple CUPS backend that can be used for avoiding writing boilerplate every time.

## Installation

1. Copy the `sample-backend` command into CUPS backend directory:

```bash
cp sample-backend /usr/lib/cups/backend/
chown root: /usr/lib/cups/backend/sample-backend
chmod 700 /usr/lib/cups/backend/sample-backend
```

2. Copy `sample.cfg` and `ppd` file into CUPS configuration directory

```bash
cp sample.cfg /etc/cups/
cp sample.ppd /etc/cups/ppd/
```
3. Restart CUPS and  check backend lists:
```bash
 lpinfo -v
```

4. To install virtual printer using this backend, run something like:
```bash
 # this will install a printer named "Sample", 
 lpadmin -p Sample \
         -v sample-backend:/ \
         -E \
         -L "Beautiful and remarkable printer." \
         -D "Best of the best!" \
         -P /etc/cups/sample.ppd
```
Well done!
