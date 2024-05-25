SHELL=/bin/bash
mkFlags?=

help:
	@echo "Help:"
	@echo "  clean    remove the downloaded files and eventualy the logs"
	@echo "  libs     install the libraries for the loaded toolchain"
	@echo "  install  install the libraries, lifex dependencies and extra packages for the loaded toolchain"

clean:
	@rm -vf */*.{tar.{bz2,gz,xz},zip,tgz}
	@find . -name "*.log" -exec rm -v '{}' \;

libs:
	@test -n "${mkToolchainBase}" && test -d "${mkToolchainBase}"
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) boost
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) tbb
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) openblas
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) blacs
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) scalapack
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) arpack
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) fftw
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) glpk
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) metis
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) scotch
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) p4est
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) suitesparse
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) mumps
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) hdf5
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) gsl
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) sundials
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) rapidjson
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) libtiff
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) libpng
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) graphicsmagick
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) lis
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) qhull
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) qrupdate
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) octave
	@"${mkPrefix}"/sbin/mkpkg $(mkFlags) octave_file_io
	##@"${mkPrefix}"/sbin/mkpkg $(mkFlags) nanoshaper

install: libs

.PHONY: help clean libs install
