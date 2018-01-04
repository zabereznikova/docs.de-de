---
title: Entwickeln von Windows-Dienstanwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 17d4c5908929f02077b1eb48932a50e83f48d076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="developing-windows-service-applications"></a>Entwickeln von Windows-Dienstanwendungen
Mithilfe von Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder der Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, Sie Dienste können problemlos erstellt durch das Erstellen einer Anwendung, die als Dienst installiert ist. Diese Art von Anwendung wird einen Windows-Dienst aufgerufen. Framework-Funktionen können Sie Dienste erstellen, zu installieren und starten, beenden und Steuern des Verhaltens.  
  
> [!WARNING]
>  Die Windows-Dienstvorlage für C++ war nicht in Visual Studio 2010 enthalten. Um ein Windows-Dienst zu erstellen, können Sie entweder einen Dienst erstellen, in verwaltetem Code in Visual c# oder Visual Basic, die mit vorhandenen C++-Code ggf. zusammenarbeiten kann, oder Sie können einen Windows-Dienst in systemeigenem C++ erstellen, mit der [ATL-Projekt-Assistent](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Bietet einen Überblick über die Windows-dienstanwendungen, die Lebensdauer von einem Dienst und dienstanwendungen wie von anderen gängigen Arten des Projekts zu unterscheiden.  
  
 [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Enthält ein Beispiel zum Erstellen eines Diensts in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] und Visual c#.  
  
 [Programmierarchitektur für Dienstanwendungen](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Erläutert die Sprachelemente in der Programmierung verwendet.  
  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Beschreibt den Prozess zum Erstellen und Konfigurieren von Windows-Diensten, die mit der Projektvorlage für Windows-Dienst.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 <xref:System.ServiceProcess.ServiceBase>  
 Beschreibt die wichtigsten Features von der <xref:System.ServiceProcess.ServiceBase> -Klasse, die zum Erstellen von Diensten verwendet wird.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Beschreibt die Funktionen von der <xref:System.ServiceProcess.ServiceProcessInstaller> Klasse, die zusammen mit verwendet wird die <xref:System.ServiceProcess.ServiceInstaller> -Klasse zum Installieren und Deinstallieren von Diensten.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Beschreibt die Funktionen von der <xref:System.ServiceProcess.ServiceInstaller> Klasse, die zusammen mit verwendet wird die <xref:System.ServiceProcess.ServiceProcessInstaller> Klasse installieren und deinstallieren den Dienst.  
  
 [NIB Erstellen von Projekten aus Vorlagen](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Beschreibt die Typen, die in diesem Kapitel und wie Sie die Auswahl zwischen diesen verwendet.
