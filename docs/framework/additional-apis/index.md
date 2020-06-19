---
title: Zusätzliche Klassenbibliotheken und APIs
description: Erkunden Sie zusätzliche Klassenbibliotheken und APIs in .net, einschließlich out-of-Band-Projekte (OOB), plattformspezifischen Bibliotheken und privaten APIs.
ms.date: 06/12/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 0b888d2f0e80685ba993682b2f3067cf8aee15bc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989732"
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

In diesem Artikel werden .NET Framework APIs aufgelistet, die entweder out-of-Band veröffentlicht wurden, eine bestimmte Plattform als Zielplattform oder private oder interne Typen sind.

## <a name="oob-projects"></a>OOB-Projekte

Um die plattformübergreifende Entwicklung zu verbessern und neue Funktionen frühzeitig einzuführen, wurden einige .NET Framework Features out-of-Band (OOB) veröffentlicht.

| Project | BESCHREIBUNG |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern. |
| <xref:System.Net.Http.WinHttpHandler> | Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit. |
| <xref:System.Numerics> | Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.|
| <xref:System.Threading.Tasks.Dataflow> | Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen. |  

## <a name="platform-specific-libraries"></a>Plattformspezifische Bibliotheken

Einige Bibliotheken richten sich an bestimmte Plattformen. Beispielsweise macht die- <xref:System.Text.CodePagesEncodingProvider> Klasse Code Page Codierungen für UWP-apps verfügbar, die mit .NET Framework entwickelt wurden.
  
| Project | BESCHREIBUNG |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Erweitert die- <xref:System.Text.EncodingProvider> Klasse, um Code Page Codierungen für Apps zur Verfügung zu stellen, die auf die universelle Windows-Plattform abzielen. |  
  
## <a name="private-apis"></a>Private APIs  

Diese APIs unterstützen die Produkt Infrastruktur und sind nicht für die direkte Verwendung im Code vorgesehen oder werden nicht unterstützt.  
  
* [Microsoft. SqlServer. Server. smiorderproperty. Item-Eigenschaft](microsoft.sqlserver.server.smiorderproperty.item.md)
* [System. Exception. prepforremoting-Methode](system.exception.prepforremoting.md)
* [System. Data. SqlTypes. SqlChars. Stream (Eigenschaft)](system.data.sqltypes.sqlchars.stream.md)
* [System. Data. SqlTypes. SqlStreamChars-Konstruktor](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [System. Data. SqlTypes. SqlStreamChars. CanSeek-Eigenschaft](system.data.sqltypes.sqlstreamchars.canseek.md)
* [System. Data. SqlTypes. SqlStreamChars. IsNull (Eigenschaft)](system.data.sqltypes.sqlstreamchars.isnull.md)
* [System. Data. SqlTypes. SqlStreamChars. length (Eigenschaft)](system.data.sqltypes.sqlstreamchars.length.md)
* [System. Data. SqlTypes. SqlStreamChars. Close-Methode](system.data.sqltypes.sqlstreamchars.close.md)
* [System. Data. SqlTypes. SqlStreamChars. verwerfen-Methode](system.data.sqltypes.sqlstreamchars.dispose.md)
* [System. Data. SqlTypes. SqlStreamChars. Flush-Methode](system.data.sqltypes.sqlstreamchars.flush.md)
* [System. Data. SqlTypes. SqlStreamChars. Read-Methode](system.data.sqltypes.sqlstreamchars.read.md)
* [System. Data. SqlTypes. SqlStreamChars. Seek-Methode](system.data.sqltypes.sqlstreamchars.seek.md)
* [System. Data. SqlTypes. SqlStreamChars. SetLength-Methode](system.data.sqltypes.sqlstreamchars.setlength.md)
* [System. Data. SqlTypes. SqlStreamChars. Write-Methode](system.data.sqltypes.sqlstreamchars.write.md)
* [System. IO. MemoryStream. internalgetoriginandlength-Methode](system.io.memorystream.internalgetoriginandlength.md)
* [System .net. comnettos-Klasse](system.net.comnetos.md)
* [System .net. Connection-Klasse](connection.md)
* [System .net. Connection. m- \_ beschreitelist-Feld](m_writelist.md)
* [System .net. connectiongroup-Klasse](connectiongroup.md)
* [Feld "System .net. connectiongroup. m \_ connectionlist"](m_connectionlist.md)
* [System .net. connectstream. Connection-Eigenschaft](system.net.connectstream.connection.md)
* [System .net. coreresponabdata-Klasse](coreresponsedata.md)
* [Feld "System .net. coreresponabdata. m \_ Response Headers"](coreresponsedata_m_responseheaders.md)
* [Feld "System .net. coreresponsedata. m" ( \_ Statuscode)](coreresponsedata_m_statuscode.md)
* [System .net. exceptionhelper-Klasse](system.net.exceptionhelper.md)
* [System .net. httpStatus Description-Klasse](system.net.httpstatusdescription.md)
* [System .net. HttpWebRequest. \_ Autoreumleitungen-Feld](_autoredirects.md)
* [System .net. HttpWebRequest. \_ Coreresponse-Feld](httpwebrequest__coreresponse.md)
* [System .net. HttpWebRequest. \_ Feld "HttpResponse"](_httpresponse.md)
* [System .net. Logging-Klasse](system.net.logging.md)
* [System .net. Mail. mailadressssparser-Klasse](system.net.mail.mailaddressparser.md)
* [System .net. Mail. quotedpaar Reader-Klasse](system.net.mail.quotedpairreader.md)
* [System .net. MIME. mailbnfhelper-Klasse](system.net.mime.mailbnfhelper.md)
* [System .net. pooledstream. NetworkStream (Eigenschaft)](system.net.pooledstream.networkstream.md)
* [System .net. rtcstate-Klasse](system.net.rtcstate.md)
* [System .net. Security. sslstate. SslProtocol (Eigenschaft)](system.net.security.sslstate.sslprotocol.md)
* [System .net. Service Point. m \_ connectiongrouplist-Feld](m_connectiongrouplist.md)
* [System .net. ServicePointManager. closeconnectiongroups-Methode](system.net.servicepointmanager.closeconnectiongroups.md)
* [System .net. ServicePointManager. s \_ servicepointtables-Feld](s_servicepointtable.md)
* [System .net. tlsstream. m_Worker-Feld](system.net.tlsstream.m_worker.md)
* [System .net. unsafenclnativemethods-Klasse](system.net.unsafenclnativemethods.md)
* [System .net. WebHeaderCollection. addinternal-Methode](system.net.webheadercollection.addinternal.md)
* [System. Service Model. Channels. Message. bodydestring-Methode](system.servicemodel.channels.message.bodytostring.md)
* [System. Service Model. Channels. Message. Write-starteaders-Methode](system.servicemodel.channels.message.writestartheaders.md)
* [System. Windows. Diagnostics. visualdiagnostics. s \_ isdebuggercheckdisabledfortesttargets-Feld](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [System. Windows. Forms. Design. DataMemberFieldEditor-Klasse](datamemberfieldeditor-class.md)
* [System. Windows. Forms. Design. datamemberlisteditor-Klasse](datamemberlisteditor-class.md)
* [System.Xml.XmlReader. kreatesqlreader-Methode](system.xml.xmlreader.createsqlreader.md)
* [ADODB. Verbindungsschnittstelle](adodb.connection.md)
* [ADODB. Eventreason-Aufzählung](adodb.eventreasonenum.md)
* [ADODB. EventStatus-Aufzählung](adodb.eventstatusenum.md)
* [stdole. Dispparameams-Struktur](stdole.dispparams.md)
* [stdole. EXCEPINFO-Struktur](stdole.excepinfo.md)
* [stdole. IFont.Name-Eigenschaft](stdole.ifont.name.md)
* [stdole. IFontDisp-Schnittstelle](stdole.ifontdisp.md)
* [stdole. IPicture. Handle-Eigenschaft](stdole.ipicture.handle.md)
* [stdole. IPictureDisp. handle (Eigenschaft)](stdole.ipicturedisp.handle.md)
* [stdole. StdFont-Schnittstelle](stdole.stdfont.md)
* [stdole. StdPicture-Schnittstelle](stdole.stdpicture.md)
  
## <a name="see-also"></a>Weitere Informationen

* [.NET Framework und Out-of-Band-Releases](../get-started/the-net-framework-and-out-of-band-releases.md)
