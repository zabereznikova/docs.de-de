---
title: "Developing Windows Service Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ServiceInstaller class, Windows Service applications"
  - "Service class, Windows Service applications"
  - "Windows Service applications"
  - "Windows NT services"
  - "ServiceProcessInstaller class, Windows Service applications"
  - "services"
  - ".NET applications, Windows applications"
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: 18
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 18
---
# Developing Windows Service Applications
Sie können Dienste mit Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oder Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK auf einfache Weise erstellen, indem Sie eine Anwendung erstellen und diese als Dienst installieren.  Dieser Anwendungstyp wird Windows\-Dienst genannt.  Mit Frameworkfeatures können Dienste erstellt und installiert werden. Darüber hinaus können diese Dienste gestartet, beendet sowie in anderer Weise gesteuert werden.  
  
> [!WARNING]
>  Die Vorlage Windows\-Dienst für C\+\+ wurde nicht in Visual Studio 2010 enthalten.  Um einen Windows\-Dienst zu erstellen, können Sie entweder einen Dienst in verwaltetem Code in Visual C\# oder Visual Basic erstellen, das mit existierendem C\+\+\-Code nach Bedarf zusammenarbeiten kann, oder Sie können einen Windows\-Dienst in systemeigenem C\+\+ erstellen mithilfe [ATL\-Projekt\-Assistent](../Topic/ATL%20Project%20Wizard.md) verwenden.  
  
## In diesem Abschnitt  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Enthält eine Übersicht über Windows\-Dienstanwendungen, die Lebensdauer eines Diensts sowie Dienstanwendungen von anderen üblichen Projekttypen unterscheiden.  
  
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Enthält ein Beispiel für das Erstellen eines Diensts in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] und Visual C\#.  
  
 [Service Application Programming Architecture](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Erläutert die Sprachelemente, die zur Programmierung von Diensten verwendet werden.  
  
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Beschreibt den Prozess des Erstellens und des Windows\-Dienste mit der Projektvorlage.  
  
## Verwandte Abschnitte  
 <xref:System.ServiceProcess.ServiceBase>  
 Beschreibt die wichtigsten Features der <xref:System.ServiceProcess.ServiceBase>\-Klasse, die zum Erstellen von Diensten verwendet wird.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Beschreibt die Features der <xref:System.ServiceProcess.ServiceProcessInstaller>\-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceInstaller>\-Klasse zum Installieren und Deinstallieren von Diensten verwendet wird.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Beschreibt die Features der <xref:System.ServiceProcess.ServiceInstaller>\-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceProcessInstaller>\-Klasse zum Installieren und Deinstallieren des Diensts verwendet wird.  
  
 [Erstellen von Projekten aus Vorlagen](http://msdn.microsoft.com/de-de/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Beschreibt die in diesem Kapitel behandelten Projekttypen und wie Sie eine Auswahl zwischen ihnen treffen.