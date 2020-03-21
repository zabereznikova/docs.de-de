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
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155907"
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

.NET Framework entwickelt sich ständig weiter. Um die plattformübergreifende Entwicklung zu verbessern und frühzeitig neue Funktionen einzuführen, werden neue Funktionen a-band (OOB) veröffentlicht. In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.  
  
Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen. Die <xref:System.Text.CodePagesEncodingProvider> Klasse stellt z. B. Codepagecodierungen für UWP-Apps zur Verfügung, die mit .NET Framework entwickelt wurden. Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.  
  
## <a name="oob-projects"></a>OOB-Projekte
  
| Project | Beschreibung |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern. |
| <xref:System.Net.Http.WinHttpHandler> | Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit. |
| <xref:System.Numerics> | Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.|
| <xref:System.Threading.Tasks.Dataflow> | Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen. |  

## <a name="platform-specific-libraries"></a>Plattformspezifische Bibliotheken
  
| Project | Beschreibung |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Erweitert die <xref:System.Text.EncodingProvider> Klasse, um Codepagecodierungen für Apps verfügbar zu machen, die auf die universelle Windows-Plattform abzielen. |  
  
## <a name="private-apis"></a>Private APIs  

Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.  
  
* [Microsoft.SqlServer.Server.SmiOrderProperty.Item-Eigenschaft](microsoft.sqlserver.server.smiorderproperty.item.md)
* [System.Exception.PrepForRemoting-Methode](system.exception.prepforremoting.md)
* [System.Data.SqlTypes.SqlChars.Stream-Eigenschaft](system.data.sqltypes.sqlchars.stream.md)
* [System.Data.SqlTypes.SqlStreamChars Konstruktor](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [System.Data.SqlTypes.SqlStreamChars.CanSeek-Eigenschaft](system.data.sqltypes.sqlstreamchars.canseek.md)
* [System.Data.SqlTypes.SqlStreamChars.IsNull-Eigenschaft](system.data.sqltypes.sqlstreamchars.isnull.md)
* [System.Data.SqlTypes.SqlStreamChars.Length-Eigenschaft](system.data.sqltypes.sqlstreamchars.length.md)
* [System.Data.SqlTypes.SqlStreamChars.Close-Methode](system.data.sqltypes.sqlstreamchars.close.md)
* [System.Data.SqlTypes.SqlStreamChars.Dispose-Methode](system.data.sqltypes.sqlstreamchars.dispose.md)
* [System.Data.SqlTypes.SqlStreamChars.Flush-Methode](system.data.sqltypes.sqlstreamchars.flush.md)
* [System.Data.SqlTypes.SqlStreamChars.Read-Methode](system.data.sqltypes.sqlstreamchars.read.md)
* [System.Data.SqlTypes.SqlStreamChars.Seek-Methode](system.data.sqltypes.sqlstreamchars.seek.md)
* [System.Data.SqlTypes.SqlStreamChars.SetLength-Methode](system.data.sqltypes.sqlstreamchars.setlength.md)
* [System.Data.SqlTypes.SqlStreamChars.Write-Methode](system.data.sqltypes.sqlstreamchars.write.md)
* [System.IO.MemoryStream.InternalGetOriginAndLength-Methode](system.io.memorystream.internalgetoriginandlength.md)
* [System.Net.Connection-Klasse](connection.md)
* [System.Net.Connection.m\_WriteList-Feld](m_writelist.md)
* [System.Net.ConnectionGroup-Klasse](connectiongroup.md)
* [System.Net.ConnectionGroup.m\_ConnectionList-Feld](m_connectionlist.md)
* [System.Net.ConnectStream.Connection-Eigenschaft](system.net.connectstream.connection.md)
* [System.Net.CoreResponseData-Klasse](coreresponsedata.md)
* [System.Net.CoreResponseData.m\_ResponseHeaders-Feld](coreresponsedata_m_responseheaders.md)
* [System.Net.CoreResponseData.m\_StatusCode-Feld](coreresponsedata_m_statuscode.md)
* [System.net.httpWebRequest. \_AutoDirects-Feld](_autoredirects.md)
* [System.net.httpWebRequest. \_CoreResponse-Feld](httpwebrequest__coreresponse.md)
* [System.net.httpWebRequest. \_HttpResponse-Feld](_httpresponse.md)
* [System.Net.PooledStream.NetworkStream-Eigenschaft](system.net.pooledstream.networkstream.md)
* [System.Net.RtcState-Klasse](system.net.rtcstate.md)
* [System.Net.ServicePoint.m\_ConnectionGroupList-Feld](m_connectiongrouplist.md)
* [System.Net.ServicePointManager.s\_ServicePointTable-Feld](s_servicepointtable.md)
* [System.Net.TlsStream.m_Worker Feld](system.net.tlsstream.m_worker.md)
* [System.Net.Security.SslState.SslProtocol-Eigenschaft](system.net.security.sslstate.sslprotocol.md)
* [System.ServiceModel.Channels.Message.BodyToString-Methode](system.servicemodel.channels.message.bodytostring.md)
* [System.ServiceModel.Channels.Message.WriteStartHeaders-Methode](system.servicemodel.channels.message.writestartheaders.md)
* [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes-Feld](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [System.Windows.Forms.Design.DataMemberFieldEditor-Klasse](datamemberfieldeditor-class.md)
* [System.Windows.Forms.Design.DataMemberListEditor-Klasse](datamemberlisteditor-class.md)
* [System.Xml.XmlReader.CreateSqlReader-Methode](system.xml.xmlreader.createsqlreader.md)
* [Adodb. Verbindungsschnittstelle](adodb.connection.md)
* [Adodb. EventReason-Enum](adodb.eventreasonenum.md)
* [Adodb. EventStatus-Enum](adodb.eventstatusenum.md)
* [stdole. DISPPARAMS-Struktur](stdole.dispparams.md)
* [stdole. EXCEPINFO-Struktur](stdole.excepinfo.md)
* [stdole. IFont.Name-Eigenschaft](stdole.ifont.name.md)
* [stdole. IFontDisp-Schnittstelle](stdole.ifontdisp.md)
* [stdole. IPicture.Handle-Eigenschaft](stdole.ipicture.handle.md)
* [stdole. IPictureDisp.Handle-Eigenschaft](stdole.ipicturedisp.handle.md)
* [stdole. StdFont-Schnittstelle](stdole.stdfont.md)
* [stdole. StdPicture-Schnittstelle](stdole.stdpicture.md)
  
## <a name="see-also"></a>Weitere Informationen

* [.NET Framework und Out-of-Band-Releases](../get-started/the-net-framework-and-out-of-band-releases.md)
