project(gloox)

find_package(OpenSSL REQUIRED)
find_package(ZLIB )

if(ZLIB_FOUND)
	add_definitions(-DHAVE_ZLIB)
endif()

include_directories(${OpenSSL_INCLUDE_DIRS})

SET( GLOOX_SRC
gloox/adhoc.cpp
gloox/amp.cpp
gloox/annotations.cpp
gloox/attention.cpp
gloox/base64.cpp
gloox/bookmarkstorage.cpp
gloox/capabilities.cpp
gloox/chatstate.cpp
gloox/chatstatefilter.cpp
gloox/clientbase.cpp
gloox/client.cpp
gloox/component.cpp
gloox/compressiondefault.cpp
gloox/compressionzlib.cpp
gloox/connectionbosh.cpp
gloox/connectionhttpproxy.cpp
gloox/connectionsocks5proxy.cpp
gloox/connectiontcpbase.cpp
gloox/connectiontcpclient.cpp
gloox/connectiontcpserver.cpp
gloox/connectiontls.cpp
gloox/connectiontlsserver.cpp
gloox/dataform.cpp
gloox/dataformfieldcontainer.cpp
gloox/dataformfield.cpp
gloox/dataformitem.cpp
gloox/dataformreported.cpp
gloox/delayeddelivery.cpp
gloox/disco.cpp
gloox/dns.cpp
gloox/error.cpp
gloox/eventdispatcher.cpp
gloox/featureneg.cpp
gloox/flexoff.cpp
gloox/gloox.cpp
gloox/gpgencrypted.cpp
gloox/gpgsigned.cpp
gloox/inbandbytestream.cpp
gloox/instantmucroom.cpp
gloox/iq.cpp
gloox/jid.cpp
gloox/lastactivity.cpp
gloox/logsink.cpp
gloox/md5.cpp
gloox/message.cpp
gloox/messageevent.cpp
gloox/messageeventfilter.cpp
gloox/messagefilter.cpp
gloox/messagesession.cpp
gloox/mucmessagesession.cpp
gloox/mucroom.cpp
gloox/mutex.cpp
gloox/nickname.cpp
gloox/nonsaslauth.cpp
gloox/oob.cpp
gloox/parser.cpp
gloox/prep.cpp
gloox/presence.cpp
gloox/privacyitem.cpp
gloox/privacymanager.cpp
gloox/privatexml.cpp
gloox/pubsubevent.cpp
gloox/pubsubitem.cpp
gloox/pubsubmanager.cpp
gloox/receipt.cpp
gloox/registration.cpp
gloox/rosteritem.cpp
gloox/rostermanager.cpp
gloox/search.cpp
gloox/sha.cpp
gloox/shim.cpp
gloox/simanager.cpp
gloox/siprofileft.cpp
gloox/socks5bytestream.cpp
gloox/socks5bytestreammanager.cpp
gloox/socks5bytestreamserver.cpp
gloox/softwareversion.cpp
gloox/stanza.cpp
gloox/stanzaextensionfactory.cpp
gloox/subscription.cpp
gloox/tag.cpp
gloox/tlsdefault.cpp
gloox/tlsgnutlsbase.cpp
gloox/tlsgnutlsclientanon.cpp
gloox/tlsgnutlsclient.cpp
gloox/tlsgnutlsserveranon.cpp
gloox/tlsopensslbase.cpp
gloox/tlsopensslclient.cpp
gloox/tlsopensslserver.cpp
gloox/tlsschannel.cpp
gloox/uniquemucroom.cpp
gloox/util.cpp
gloox/vcard.cpp
gloox/vcardmanager.cpp
gloox/vcardupdate.cpp
gloox/xhtmlim.cpp
)

add_library(gloox STATIC ${GLOOX_SRC})
target_link_libraries(gloox  ${OPENSSL_LIBRARIES})
if(UNIX)
	target_link_libraries(gloox -pthread)
endif()