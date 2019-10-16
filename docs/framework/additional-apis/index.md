---
title: Zusätzliche Klassenbibliotheken und APIs
ms.date: 10/09/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: b869ca2f5e17db9a204a8b757b5e24ebb209d7c5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395660"
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

Die .NET Framework wird ständig weiterentwickelt. Um die plattformübergreifende Entwicklung zu verbessern und frühzeitig neue Funktionen einzuführen, werden neue Features out-of-Band (OOB) veröffentlicht. In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.  
  
Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen. Beispielsweise macht die Klasse <xref:System.Text.CodePagesEncodingProvider> Code Page Codierungen für UWP-apps verfügbar, die mithilfe des .NET Framework entwickelt wurden. Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.  
  
## <a name="oob-projects"></a>OOB-Projekte
  
| Projekt | Beschreibung |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern. |
| <xref:System.Net.Http.WinHttpHandler> | Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit. |
| <xref:System.Numerics> | Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.| 
| <xref:System.Threading.Tasks.Dataflow> | Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen. |  

## <a name="platform-specific-libraries"></a>Plattformspezifische Bibliotheken
  
| Projekt | Beschreibung |  
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
* [System .net. Connection-Klasse](connection.md)
* [System .net. Connection. m @ no__t-1schreitelist-Feld](m_writelist.md)
* [System .net. connectiongroup-Klasse](connectiongroup.md)
* [System .net. connectiongroup. m @ no__t-1connectionlist-Feld](m_connectionlist.md)
* [System .net. coreresponabdata-Klasse](coreresponsedata.md)
* [System .net. coreresponabdata. m @ no__t-1response Headers-Feld](coreresponsedata_m_responseheaders.md)
* [System .net. coreresponsedata. m @ no__t-1Status Code-Feld](coreresponsedata_m_statuscode.md)
* [System .net. HttpWebRequest. \_autoreumleitungen-Feld](_autoredirects.md)
* [System .net. HttpWebRequest. \_coreresponse-Feld](httpwebrequest__coreresponse.md)
* [System .net. HttpWebRequest. \_httpresponse-Feld](_httpresponse.md)
* [System .net. Service Point. m @ no__t-1connectiongrouplist-Feld](m_connectiongrouplist.md)
* [System .net. ServicePointManager. s @ no__t-1servicepoint\feld](s_servicepointtable.md)
* [System. Windows. Diagnostics. visualdiagnostics. s @ no__t-1isdebuggercheckdisabledfortesttargets-Feld](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [System. Windows. Forms. Design. DataMemberFieldEditor-Klasse](datamemberfieldeditor-class.md)
* [System. Windows. Forms. Design. datamemberlisteditor-Klasse](datamemberlisteditor-class.md)
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
  
## <a name="see-also"></a>Siehe auch

* [.NET Framework und Out-of-Band-Releases](../get-started/the-net-framework-and-out-of-band-releases.md)
