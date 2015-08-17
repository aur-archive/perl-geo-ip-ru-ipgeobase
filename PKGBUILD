pkgname='perl-geo-ip-ru-ipgeobase'
pkgver='0.03'
pkgrel='1'
pkgdesc="Geo::IP::RU::IpGeoBase - look up location by IP address in Russia"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl' 'perl-libwww' 'perl-dbi')
makedepends=()
url='http://search.cpan.org/perldoc?Geo%3A%3AIP%3A%3ARU%3A%3AIpGeoBase'
source=("http://search.cpan.org/CPAN/authors/id/R/RU/RUZ/Geo-IP-RU-IpGeoBase-${pkgver}.tar.gz")
md5sums=('87f235d05ccc4f0fe7291c903900ac69')

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "${srcdir}/Geo-IP-RU-IpGeoBase-$pkgver" 
    /usr/bin/perl Makefile.PL
    make
  )
}

check() {
  cd "${srcdir}/Geo-IP-RU-IpGeoBase-$pkgver"
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "${srcdir}/Geo-IP-RU-IpGeoBase-$pkgver"
  make install
  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}

