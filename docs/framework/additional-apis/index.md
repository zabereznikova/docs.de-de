---
title: Zusätzliche Klassenbibliotheken und APIs
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 7659dde4a2cb08fc3257d2f613ce4146522072b6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706264"
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

.NET Framework wird ständig weiterentwickelt. Um plattformübergreifende Entwicklung zu verbessern und eine neue Funktionalität einem frühen Zeitpunkt einführen, werden neue Features of-Band (OOB) veröffentlicht. In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.  
  
Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen. Z. B. die <xref:System.Text.CodePagesEncodingProvider> -Klasse stellt codepagecodierungen für UWP-apps mit .NET Framework entwickelt wurden. Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.  
  
## <a name="oob-projects"></a>OOB-Projekte
  
| Projekt | Beschreibung |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern. |
| <xref:System.Net.Http.WinHttpHandler> | Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit. |
| [System.Numerics.Vectors](https://msdn.microsoft.com/library/mt452176.aspx) | Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.| 
| <xref:System.Threading.Tasks.Dataflow> | Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen. |  

## <a name="platform-specific-libraries"></a>Plattformspezifische Bibliotheken
  
| Projekt | Beschreibung |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Erweitert die <xref:System.Text.EncodingProvider> Klasse, um codepagecodierungen für apps zur Verfügung stellen, die auf die universelle Windows-Plattform abzielen. |  
  
## <a name="private-apis"></a>Private APIs  

Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.  
  
| Name der API |
| -------- |
| [System.Net.Connection-Klasse](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList-Feld](../../../docs/framework/additional-apis/m_writelist.md) |
| [System.Net.ConnectionGroup-Klasse](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList Field](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.Net.CoreResponseData-Klasse](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [System.Net.CoreResponseData.m\_ResponseHeaders Field](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [System.Net.CoreResponseData.m\_StatusCode-Feld](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [System.Net.HttpWebRequest. \_AutoRedirects-Feld](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.HttpWebRequest. \_CoreResponse-Feld](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [System.Net.HttpWebRequest. \_HttpResponse-Feld](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList-Feld](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable-Feld](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [System.Windows.Forms.Design.DataMemberFieldEditor Class](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [System.Windows.Forms.Design.DataMemberListEditor Class](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Siehe auch

[.NET Framework und Out-of-Band-Releases](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
