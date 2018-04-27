---
title: Konfigurieren der Anwendung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 922b9c5c53e04719f3ed48d0ff6386f21bf83e99
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="configuring-your-application"></a>Konfigurieren der Anwendung
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet das .NET-Konfigurationssystem und ermöglicht es Ihnen, computer- und anwendungsspezifische Dienste zu konfigurieren.  
  
 Von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definierte Konfigurationseinstellungen befinden sich in der `<system.serviceModel>`-Abschnittsgruppe. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Konfigurieren eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts finden Sie in den folgenden Themen:  
  
-   [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Anwendungseinstellungen in Konfigurationsdateien .NET finden Sie unter [ \<"appSettings" >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor  
 Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) ermöglicht Administratoren und Entwickler erstellen und Ändern von Konfigurationseinstellungen für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienste mit einer grafischen Benutzeroberfläche. Mit diesem Tool können Sie die Einstellungen für Bindungen, Verhaltensweisen, Dienste und Diagnosen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwalten, ohne XML-Dateien direkt bearbeiten zu müssen.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Bearbeiten von Konfigurationsdateien in Visual Studio  
 So bearbeiten Sie die Konfigurationsdatei von einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienstprojekt in Visual Studio, mit der rechten Maustaste in **Projektmappen-Explorer** , und wählen Sie die **WCF-Konfiguration bearbeiten** Kontextmenüelement. Dadurch wird die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Wenn Sie die Konfigurationsdatei des Bearbeiten einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service-Projekt in Visual Studio mit der rechten Maustaste in **Projektmappen-Explorer**, beachten Sie, dass die **WCF-Konfiguration bearbeiten** Kontextmenüelement ist nicht vorhanden. Zur Umgehung dieses Problem, klicken Sie auf die **Tools** Menü, und wählen Sie **WCF-Dienstkonfigurations-Editor**. Danach können Sie mit der rechten Maustaste einer Konfigurationsdatei und die **WCF-Konfiguration bearbeiten** Kontextmenüelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
