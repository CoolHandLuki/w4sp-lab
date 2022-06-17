Update for Kali 2022.2 in progress. Currently all docker images are building and running but the lab itself doesn't work.

If you want to run it anyhow run:
```
git clone https://github.com/CoolHandLuki/w4sp-lab
cd w4sp-lab
sudo python3 w4sp_webapp.py
```

To get everything running up to this point the following was changed:
- Update print statements to python3
- Make import statements use relative paths
- Update generator syntax to use next(generator) instead of generator.next()
- Update dockerfiles to use Ubuntu 22.04 LTS as a base instead of Ubuntu 14.04 LTS
- Some changes inside the apt-get install and pip install

---
Old README.md instructions are below:

 !!! PLEASE REFER TO THE MOST RECENT UPDATED INSTALLATION INSTRUCTIONS [HERE](https://github.com/w4sp-book/w4sp-lab/wiki/Lab-Installation)  !!!!

This is the lab environment for the Wireshark for Security Professionals book. The lab is built on
top of Docker and Kali Linux and provides a realistic network with numerous services useful for learning security fundamentals with Wireshark.

Both Kali and the w4sp-lab are moving targets and are subject to change. Always refer to the [wiki](https://github.com/w4sp-book/w4sp-lab/wiki) for the most recent information regarding working with the lab.
