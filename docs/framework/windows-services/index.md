---
title: Entwickeln von Windows-Dienstanwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: 2c7fb148b96d5ff9804bcb0bb7c842c475c0f117
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207095"
---
# <a name="developing-windows-service-applications"></a>Entwickeln von Windows-Dienstanwendungen
Über Microsoft Visual Studio oder das Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK können Dienste problemlos erstellt werden, indem eine Anwendung erstellt und als Dienst installiert wird. Dieser Anwendungstyp wird als Windows-Dienst bezeichnet. Mit Frameworkfeatures können Sie Dienste erstellen, diese installieren, starten, beenden oder auch auf andere Weise deren Verhalten steuern.  
  
> [!WARNING]
>  Die Windows-Dienstvorlage für C++ war in Visual Studio 2010 nicht enthalten. Um einen Windows-Dienst zu erstellen, können Sie entweder einen Dienst in verwaltetem Code in Visual C# oder Visual Basic erstellen, der ggf. mit vorhandenem C++-Code zusammenarbeitet, oder Sie können über den [ATL-Projekt-Assistenten](/cpp/atl/reference/atl-project-wizard) einen Windows-Dienst in der nativen Sprache C++ erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Stellt eine Übersicht von Windows-Dienstanwendungen bereit, wie die Lebensdauer eines Dienst und wie Dienstanwendungen sich von anderen häufigen Projekttypen unterscheiden  
  
 [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Stellt ein Beispiel zur Erstellung eines Diensts in Visual Basic und Visual C# bereit  
  
 [Programmierarchitektur für Dienstanwendungen](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Erläutert die Sprachelemente, die in der Dienstprogrammierung verwendet werden  
  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Beschreibt den Vorgang des Erstellens und Konfigurierens von Windows-Diensten über die Windows-Dienstprojektvorlage  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 <xref:System.ServiceProcess.ServiceBase>  
 Beschreibt die Hauptfeatures der <xref:System.ServiceProcess.ServiceBase>-Klasse, die zum Erstellen von Diensten verwendet wird  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Beschreibt die Features der <xref:System.ServiceProcess.ServiceProcessInstaller>-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceInstaller>-Klasse zum Installieren und Deinstallieren Ihrer Dienste verwendet wird  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Beschreibt die Features der <xref:System.ServiceProcess.ServiceInstaller>-Klasse, die zusammen mit der <xref:System.ServiceProcess.ServiceProcessInstaller>-Klasse zum Installieren und Deinstallieren Ihres Diensts verwendet wird  
  
 [NIB: Erstellen von Projekten aus Vorlagen](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Beschreibt die Projekttypen, die in diesem Kapitel verwendet werden und wie Sie aus Ihnen wählen
