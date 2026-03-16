# mfsk-olivia

Original MFSK/Olivia modem source code by Pawel Jalocha, reorganized into a more conventional C/C++ project layout without changing the implementation itself.

## Layout

- `apps/`: interactive end-user binaries
- `include/mfsk/`: shared project headers
- `tools/`: offline utilities and analysis programs
- `tests/`: simulation-style test program
- `docs/`: license and original release notes
- `legacy/`: original legacy build file preserved for reference

## Binaries

Applications:

- `mfsk_tx`
- `mfsk_rx`
- `mfsk_trx`

Tools:

- `mfsk_encode`
- `mfsk_symb`
- `rate_check`
- `peakrms`
- `addnoise`
- `addcarr`

Test program:

- `mfsk_test`

## Build

Preferred:

```sh
cmake -S . -B build
cmake --build build
```

Compatibility wrapper:

```sh
make
```

## Notes

- Source contents were not rewritten as part of this reorganization.
- The original release notes are in `docs/original-release-notes.txt`.
- The original Linux makefile is preserved as `legacy/Makefile.linux`.
