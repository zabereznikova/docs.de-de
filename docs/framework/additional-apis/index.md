---
title: "Zusätzliche Klassenbibliotheken und APIs"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3bb7a7c53cbca8bbd4026b46ce59589cef22382
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="additional-class-libraries-and-apis"></a>Zusätzliche Klassenbibliotheken und APIs

Um die plattformübergreifende Entwicklung für das sich ständig weiterentwickelnde .NET Framework für unsere Kunden rechtzeitig zu verbessern oder neue Funktionalität einzuführen, werden neue Funktionen out-of-band (OOB) veröffentlicht. In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.  
  
Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen. Z. B. die <xref:System.Text.CodePagesEncodingProvider> Klasse stellt codepagecodierungen uwp-apps mit .NET Framework entwickelt wurden zur Verfügung. Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.  
  
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
| <xref:System.Text.CodePagesEncodingProvider> | Erweitert die <xref:System.Text.EncodingProvider> Klasse, um die codepagecodierungen für apps verfügbar zu machen, die auf Uwp abzielen. |  
  
## <a name="private-apis"></a>Private APIs  

Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.  
  
| Name der API |
| -------- |
| [System.Net.Connection-Klasse](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList-Feld](../../../docs/framework/additional-apis/m_writelist.md) |
| [System.Net.ConnectionGroup-Klasse](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList-Feld](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.NET.HttpWebRequest". \_HttpResponse-Feld](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.NET.HttpWebRequest". \_AutoRedirects-Feld](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList-Feld](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable-Feld](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_IsDebuggerCheckDisabledForTestPurposes Feld](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [System.Windows.Forms.Design.DataMemberFieldEditor-Klasse](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [System.Windows.Forms.Design.DataMemberListEditor-Klasse](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Siehe auch

[.NET Framework und Out-of-Band-Releases](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
