
FULL_LIBEXECDIR=$(libexecdir)

desktopdir = $(sysconfdir)/xdg/autostart
desktop_DATA = polkit-mate-authentication-agent-1.desktop

@INTLTOOL_DESKTOP_RULE@

polkit-mate-authentication-agent-1.desktop.in : polkit-mate-authentication-agent-1.desktop.in.in Makefile
	$(AM_V_GEN)sed \
		-e "s|\@FULL_LIBEXECDIR\@|$(FULL_LIBEXECDIR)|" \
		$< > $@

libexec_PROGRAMS = polkit-mate-authentication-agent-1

polkit_mate_authentication_agent_1_SOURCES = 						\
	polkitmatelistener.h			polkitmatelistener.c			\
	polkitmateauthenticator.h		polkitmateauthenticator.c		\
	polkitmateauthenticationdialog.h	polkitmateauthenticationdialog.c	\
	main.c										\
	$(BUILT_SOURCES)

polkit_mate_authentication_agent_1_CPPFLAGS = 		\
	-I$(top_srcdir)					\
	-DG_LOG_DOMAIN=\"polkit-mate-1\"		\
	-DDATADIR=\""$(pkgdatadir)"\"			\
	-DMATELOCALEDIR=\""$(datadir)/locale"\"	\
	-DPOLKIT_AGENT_I_KNOW_API_IS_SUBJECT_TO_CHANGE	\
	$(AM_CPPFLAGS)

polkit_mate_authentication_agent_1_CFLAGS = 		\
	$(GTK_CFLAGS)					\
	$(GLIB_CFLAGS)					\
	$(POLKIT_AGENT_CFLAGS)				\
	$(POLKIT_GOBJECT_CFLAGS)			\
	$(APPINDICATOR_CFLAGS)				\
	$(WARN_CFLAGS)					\
	$(AM_CFLAGS)

polkit_mate_authentication_agent_1_LDFLAGS = 		\
	$(AM_LDFLAGS)

polkit_mate_authentication_agent_1_LDADD = 		\
	$(GTK_LIBS)					\
	$(GLIB_LIBS)					\
	$(POLKIT_AGENT_LIBS)				\
	$(POLKIT_GOBJECT_LIBS)				\
	$(APPINDICATOR_LIBS)				\
	$(INTLLIBS)

EXTRA_DIST = \
	polkit-mate-authentication-agent-1.desktop.in \
	polkit-mate-authentication-agent-1.desktop.in.in

clean-local :
	rm -f *~ polkit-mate-authentication-agent-1.desktop polkit-mate-authentication-agent-1.desktop.in
