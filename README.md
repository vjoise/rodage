<p align="center">
  <a href="https://vjoise.github.io/rodage/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="brand/logo-dark.png">
      <img src="brand/logo-light.png" alt="Rodage" width="300">
    </picture>
  </a>
</p>

Every new GPU rack gets burned in before it goes live. The results usually end up spread across log files, spreadsheets and screenshots, and a few months later nobody can say which serial failed which test, or why a tray was swapped.

Rodage is my attempt to fix that. It's a service that schedules tests wherever you need them: a whole building, a hall, a row, a single rack or one host. The results show up at every level too. You can start from the building, see which racks have problems, open a rack, then a host, and end up at the exact GPU, drive or power supply that failed. Every run is kept as a record you can look back at, or hand to a customer or a vendor.

It's meant to sit on top of the tools you already use: DCGM, NCCL tests, nvme-cli and Redfish for testing, and NetBox or a spreadsheet for knowing what's where.

```console
$ rdg schedule rack B02 --profile gb200-burnin --at 22:00
$ rdg schedule host b02-ct5 --profile gpu-recheck
$ rdg status hall H1
  B01  pass
  B02  1 warning   b02-ct5 gpu2 at 90.5% of fleet bandwidth
  B03  running     stage 2 of 4
```

## Where it stands

It's early. I have a working prototype of the rack and parts view, and test execution is what I'm building next. The code will go up here, open source, once the first version is usable. For now this repo holds the [website](https://vjoise.github.io/rodage/).

## Why "rodage"?

It's French for breaking in: running a new engine gently before you work it hard. That's what burn-in is for servers.

## Say hello

If you look after GPU hardware and this sounds familiar, I'd like to hear how you handle it today. Start a thread in [Discussions](https://github.com/vjoise/rodage/discussions).
