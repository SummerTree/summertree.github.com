---
layout: post
title: "build lib for iOS"
categories: [iOS]
tags: [iOS]
---

	#! /bin/bash
	
	export MINVER="5.1" # the minimum supported OS version
	export SDKVER="6.1" # SDK version
	export PREFIX="$HOME/built-for-ios" # where the library goes
	
	export DEVROOT="/Applications/Xcode4.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer"
	export SDKROOT="${DEVROOT}/SDKs/iPhoneOS${SDKVER}.sdk"
	export PKG_CONFIG_LIBDIR="${PREFIX}/lib/pkgconfig:${SDKROOT}/usr/lib/pkgconfig"
	export COMMON_FLAGS="-arch armv7s -isysroot ${SDKROOT}"
	export CPPFLAGS="-I${PREFIX}/include ${COMMON_FLAGS} -miphoneos-version-min=${MINVER}"
	export CFLAGS="${CPPFLAGS}"
	export LDFLAGS="-L${PREFIX}/lib ${COMMON_FLAGS} -Wl,-iphoneos_version_min,${MINVER}"
	export CC="${DEVROOT}/usr/bin/gcc"
	export CXX="${DEVROOT}/usr/bin/g++"
	export OBJC="${CC}"
	export LD="${CC}"
	
	[ ! -d "${PREFIX}" ] && mkdir -p "${PREFIX}"
	./configure --prefix="${PREFIX}" \
	--build="x86_64-apple-darwin" \
	--host="arm-apple-darwin" \
	--enable-static \
	--disable-shared \
	glib_cv_stack_grows=no \
	glib_cv_uscore=no \
	ac_cv_func_posix_getgrgid_r=yes \
	ac_cv_func_posix_getpwuid_r=yes
	
