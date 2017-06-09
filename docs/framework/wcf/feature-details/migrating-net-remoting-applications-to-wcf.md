---
title: "Migrieren von .NET-Remoteanwendungen nach WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ", NET-Remoting [WCF]"
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Migrieren von .NET-Remoteanwendungen nach WCF
**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird.Verteilte Anwendungen sollten jetzt mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] entwickelt werden.**  
  
 Es gibt zwei Möglichkeiten, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit vorhandenen .NET\-Remoting\-Anwendungen zu nutzen: Integration und Migration.Bei der Integration können .Net Remoting 2.0 und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nebeneinander ausgeführt werden. So können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar machen, ohne den vorhandenen .Net Remoting 2.0\-Code ändern zu müssen.Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird.Wenn Sie die Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nutzen möchten und keine Übertragungskompatibilität mit Remoting 2.0\-Systemen benötigen, können Sie eine Migration des gesamten Diensts nach [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durchführen.Eine Migration von .NET Remoting 2.0 nach [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] setzt Änderungen an der Schnittstelle des Remoteobjekts und seinen Konfigurationseinstellungen voraus.Beide Themen werden in [Von Remoting zu Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403) behandelt.  
  
## Siehe auch  
 [Konzeptionelle Übersicht](../../../../docs/framework/wcf/conceptual-overview.md)