---
title: Zusätzliche Klassenbibliotheken und APIs
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 3a5134aa4407598e223fd2c938bfaac02cf9178c
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215536"
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

Die .NET Framework wird ständig weiterentwickelt. Um die plattformübergreifende Entwicklung zu verbessern und frühzeitig neue Funktionen einzuführen, werden neue Features out-of-Band (OOB) veröffentlicht. In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.  
  
Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen. Beispielsweise macht die <xref:System.Text.CodePagesEncodingProvider>-Klasse Code Page Codierungen für UWP-apps verfügbar, die mithilfe des .NET Framework entwickelt wurden. Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.  
  
## <a name="oob-projects"></a>OOB-Projekte
  
| Project | BESCHREIBUNG |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern. |
| <xref:System.Net.Http.WinHttpHandler> | Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit. |
| <xref:System.Numerics> | Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.| 
| <xref:System.Threading.Tasks.Dataflow> | Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen. |  

## <a name="platform-specific-libraries"></a>Plattformspezifische Bibliotheken
  
| Project | BESCHREIBUNG |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Erweitert die <xref:System.Text.EncodingProvider>-Klasse, um Code Page Codierungen für Apps zur Verfügung zu stellen, die auf die universelle Windows-Plattform abzielen. |  
  
## <a name="private-apis"></a>Private APIs  

Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.  
  
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
* [System .net. Connection-Klasse](connection.md)
* [System .net. Connection. m\_beschreitelist-Feld](m_writelist.md)
* [System .net. connectiongroup-Klasse](connectiongroup.md)
* [System .net. connectiongroup. m\_connectionlist-Feld](m_connectionlist.md)
* [System .net. connectstream. Connection-Eigenschaft](system.net.connectstream.connection.md)
* [System .net. coreresponabdata-Klasse](coreresponsedata.md)
* [System .net. coreresponabdata. m\_Response Headers-Feld](coreresponsedata_m_responseheaders.md)
* [System .net. coreresponsedata. m\_Feld "Statuscode"](coreresponsedata_m_statuscode.md)
* [System .net. HttpWebRequest.\_autoreumleitungen-Feld](_autoredirects.md)
* [Feld "System .net. HttpWebRequest.\_coreresponse"](httpwebrequest__coreresponse.md)
* [Feld "System .net. HttpWebRequest.\_HttpResponse"](_httpresponse.md)
* [System .net. pooledstream. NetworkStream (Eigenschaft)](system.net.pooledstream.networkstream.md)
* [System .net. rtcstate-Klasse](system.net.rtcstate.md)
* [System .net. Service Point. m\_connectiongrouplist-Feld](m_connectiongrouplist.md)
* [Feld "System .net. ServicePointManager. s\_servicepoin\"](s_servicepointtable.md)
* [System .net. tlsstream. m_Worker-Feld](system.net.tlsstream.m_worker.md)
* [System .net. Security. sslstate. SslProtocol (Eigenschaft)](system.net.security.sslstate.sslprotocol.md)
* [System. Service Model. Channels. Message. bodydestring-Methode](system.servicemodel.channels.message.bodytostring.md)
* [System. Service Model. Channels. Message. Write-starteaders-Methode](system.servicemodel.channels.message.writestartheaders.md)
* [System. Windows. Diagnostics. visualdiagnostics. s\_isdebuggercheckdisabledfortesttargets-Feld](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [System. Windows. Forms. Design. DataMemberFieldEditor-Klasse](datamemberfieldeditor-class.md)
* [System. Windows. Forms. Design. datamemberlisteditor-Klasse](datamemberlisteditor-class.md)
* [System. Xml. XmlReader. kreatesqlreader-Methode](system.xml.xmlreader.createsqlreader.md)
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
