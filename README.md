<p align="center">
  <a href="https://vjoise.github.io/rodage/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="brand/logo-dark.png">
      <img src="brand/logo-light.png" alt="Rodage" width="320">
    </picture>
  </a>
</p>

<p align="center"><strong>Burn-in, proven.</strong><br>Open, vendor-neutral test execution for GPU data centers.</p>

<p align="center">
  <a href="https://vjoise.github.io/rodage/"><img src="https://img.shields.io/badge/website-vjoise.github.io%2Frodage-e8532a" alt="Website"></a>
  <img src="https://img.shields.io/badge/status-early%20development-f59a3c" alt="Status: early development">
  <a href="https://github.com/vjoise/rodage/discussions"><img src="https://img.shields.io/badge/discussions-join-2e9d62" alt="Discussions"></a>
</p>

---

**Rodage** runs burn-in tests on GPU racks, shows every result on the rack and the exact part that failed, and leaves a record you can hand to a customer, a vendor or an auditor.

*Rodage* (roh-DAHZH) is French for **breaking in**, the running-in of new machinery before it goes to work.

## How it works

| Step | What happens |
| --- | --- |
| **Define** | Describe the floor, racks and cabling in YAML, or import them from NetBox or a spreadsheet. Shapes such as DGX B200 and GB200 NVL72 come from a shared catalog. |
| **Run** | Run a versioned burn-in profile on a host, rack or row with `rdg run`. Rodage drives DCGM, NCCL tests, nvme-cli and Redfish. |
| **See** | Each tray, GPU, drive and power supply turns green, amber or red on a drawing of the rack, with the error and its history one click away. |
| **Prove** | Every run becomes an append-only record with serials, firmware and log hashes, ready for acceptance, RMA or supplier handover. |

```console
$ rdg run rack B02 --profile gb200-burnin
  gpu-diagnostics   72/72 GPUs   pass
  nccl-allreduce    18/18 trays  warn  b02-ct5 gpu2 at 90.5%
  power-redundancy  48/48 PSUs   pass
```

## Who it's for

DC Ops teams at GPU clouds, colocation providers, HPC and research centers, and system integrators who ship racks with burn-in evidence.

## Status

Early development. A prototype covers the site definition, the rack and FRU console and a validator; test execution is next. The code will be published here under Apache 2.0 when v0.1 is ready.

If you run GPU hardware and want to shape what gets built, say hello in [Discussions](https://github.com/vjoise/rodage/discussions).

## This repository

This repository currently holds the [project website](https://vjoise.github.io/rodage/). The logo and social preview are in [`brand/`](brand/).
