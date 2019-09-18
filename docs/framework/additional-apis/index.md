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
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053243"
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

Die .NET Framework wird ständig weiterentwickelt. Um die plattformübergreifende Entwicklung zu verbessern und frühzeitig neue Funktionen einzuführen, werden neue Features out-of-Band (OOB) veröffentlicht. In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.  
  
Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen. Beispielsweise macht die <xref:System.Text.CodePagesEncodingProvider> -Klasse Code Page Codierungen für UWP-apps verfügbar, die mithilfe des-.NET Framework entwickelt wurden. Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.  
  
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
| <xref:System.Text.CodePagesEncodingProvider> | Erweitert die <xref:System.Text.EncodingProvider> -Klasse, um Code Page Codierungen für Apps zur Verfügung zu stellen, die auf die universelle Windows-Plattform abzielen. |  
  
## <a name="private-apis"></a>Private APIs  

Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.  
  
| Name der API |
| -------- |
| [System .net. Connection-Klasse](connection.md) |
| [System .net. Connection. m\_-beschreitelist-Feld](m_writelist.md) |
| [System .net. connectiongroup-Klasse](connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList Field](m_connectionlist.md) |
| [System .net. coreresponabdata-Klasse](coreresponsedata.md) |
| [System.Net.CoreResponseData.m\_ResponseHeaders Field](coreresponsedata_m_responseheaders.md) |
| [Feld "System .net. coreresponsedata\_. m" (Statuscode)](coreresponsedata_m_statuscode.md) |
| [System .net. HttpWebRequest. \_Autoreumleitungen-Feld](_autoredirects.md) |
| [System .net. HttpWebRequest. \_Coreresponse-Feld](httpwebrequest__coreresponse.md) |
| [System .net. HttpWebRequest. \_Feld "HttpResponse"](_httpresponse.md) |
| [System .net. Service Point. m\_connectiongrouplist-Feld](m_connectiongrouplist.md) |
| [System .net. ServicePointManager. s\_servicepointtables-Feld](s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [System.Windows.Forms.Design.DataMemberFieldEditor Class](datamemberfieldeditor-class.md) |
| [System.Windows.Forms.Design.DataMemberListEditor Class](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Siehe auch

- [.NET Framework und Out-of-Band-Releases](../get-started/the-net-framework-and-out-of-band-releases.md)
