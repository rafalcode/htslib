CC=gcc
# you most definitely will have to change these two:
CUTTINGEDGECOMPILEDLIBLOCATION=-L/home/nutria/mylocal/lib
CUTTINGEDGECOMPILEDHDRLOCATION=-I/home/nutria/mylocal/include
CFLAGS=-g -Wall ${CUTTINGEDGECOMPILEDHDRLOCATION}
SPECLIBS=${CUTTINGEDGECOMPILEDLIBLOCATION} -lhts -lm -pthread
EXECUTABLES_X=sam test-regidx test-vcf-api test-vcf-sweep test_view fieldarith hfile
EXECUTABLES=sam test-regidx test-vcf-api test-vcf-sweep fieldarith hfile
DATAFILES= rmme0.bcf rmme.bcf rmme.bcf.csi

default: ${EXECUTABLES}

sam: sam.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

test-regidx: test-regidx.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

# initially this si the most interesting of the tests .. programmer recommended it too 
test-vcf-api: test-vcf-api.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

test-vcf-sweep: test-vcf-sweep.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

test_view: test_view.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

fieldarith: fieldarith.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

hfile: hfile.c
	${CC} ${CFLAGS} -o $@ $^ ${SPECLIBS}

.PHONY: clean

clean:
	rm -f ${EXECUTABLES} ${DATAFILES}
