QUICKNOTE RF Fork of "develop" branch: no code changes, purely copy-and-modification of test directory
into one called apiexamples where the test code is commented and refactored for
standalone api usage. 

HTSlib is an implementation of a unified C library for accessing common file
formats, such as [SAM, CRAM and VCF][1], used for high-throughput sequencing
data, and is the core library used by [samtools][2] and [bcftools][3].
HTSlib only depends on [zlib][4].
It is known to be compatible with gcc, g++ and clang.

HTSlib implements a generalized BAM index, with file extension `.csi`
(coordinate-sorted index). The HTSlib file reader first looks for the new index
and then for the old if the new index is absent.

This project also includes the popular tabix indexer, which indexes both `.tbi`
and `.csi` formats, and the bgzip compression utility.

[1]: http://samtools.github.io/hts-specs/
[2]: http://github.com/samtools/samtools
[3]: http://samtools.github.io/bcftools/
[4]: http://zlib.net/

### Building HTSlib

See [INSTALL](INSTALL) for complete details.
[Release tarballs][download] contain generated files that have not been
committed to this repository, so building the code from a Git repository
requires an extra step:

```sh
autoconf       # Generate the configure script, if needed
./configure    # Optional, needed for choosing optional functionality
make
make install
```

[download]: http://www.htslib.org/download/
