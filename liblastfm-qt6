%define major 1
%define libname %mklibname lastfm-qt6
%define libnamefinger %mklibname lastfm_fingerprint-qt6
%define devname %mklibname lastfm-qt6 -d

%define git .20250222

Summary:	Liblastfm is a collection of libraries to help you integrate Last.fm services
Name:		liblastfm-qt6
Version:	1.2.0%{git}
Release:	1
License:	GPLv3
Group:		System/Libraries
Url:		https://github.com/lastfm/liblastfm
#Source0:	https://github.com/lastfm/liblastfm/archive/%{version}/%{name}-%{version}.tar.gz
# alive fork
Source0:  https://github.com/Mazhoon/liblastfm/archive/refs/heads/liblastfm-dev.tar.gz

BuildRequires:	cmake
BuildRequires:  make
BuildRequires:	ruby
BuildRequires:	pkgconfig(samplerate)
BuildRequires:	pkgconfig(fftw3)
BuildRequires:  cmake(Qt6Core)
BuildRequires:  cmake(Qt6DBus)
BuildRequires:  cmake(Qt6Network)
BuildRequires:  cmake(Qt6Sql)
BuildRequires:  cmake(Qt6Test)
BuildRequires:  cmake(Qt6Xml)

%description
Liblastfm is a collection of libraries to help you integrate Last.fm services
into your rich desktop software. It is officially supported software developed
by Last.fm staff.

%package -n %{libname}
Group:		System/Libraries
Summary:	Liblastfm is a collection of libraries to help you integrate Last.fm services

%description -n %{libname}
Liblastfm is a collection of libraries to help you integrate Last.fm services
into your rich desktop software. It is officially supported software developed
by Last.fm staff.

%package -n %{libnamefinger}
Group:		System/Libraries
Summary:	Liblastfm is a collection of libraries to help you integrate Last.fm services

%description -n %{libnamefinger}
Liblastfm is a collection of libraries to help you integrate Last.fm services
into your rich desktop software. It is officially supported software developed
by Last.fm staff.

%package -n %{devname}
Group:		Development/C
Summary:	%{name} development header
Requires:	%{libname} = %{version}-%{release}
Requires:	%{libnamefinger} = %{version}-%{release}
Provides:	%{name}-devel = %{version}-%{release}

%description -n %{devname}
Install this package if you want do compile applications i
using the libtag library.

%prep
%autosetup -n liblastfm-dev -p1

%build

%cmake -DBUILD_FINGERPRINT=ON -DBUILD_WITH_QT5=OFF ../..
%make_build

%install
%make_install -C build

%files -n %{libname}
%{_libdir}/liblastfm6.so.%{major}*

%files -n %{libnamefinger}
%{_libdir}/liblastfm_fingerprint6.so.%{major}*

%files -n %{devname}
%doc COPYING
%{_libdir}/liblastfm6.so
%{_libdir}/liblastfm_fingerprint6.so
%{_includedir}/*
%{_libdir}/cmake/lastfm6/


