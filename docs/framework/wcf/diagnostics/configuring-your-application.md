---
title: "Konfigurieren der Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Konfigurieren der Anwendung
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet das .NET\-Konfigurationssystem und ermöglicht es Ihnen, computer\- und anwendungsspezifische Dienste zu konfigurieren.  
  
 Von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definierte Konfigurationseinstellungen befinden sich in der `<system.serviceModel>`\-Abschnittsgruppe.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Konfigurieren eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts finden Sie in den folgenden Themen:  
  
-   [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`\-Abschnittsgruppe definiert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Anwendungseinstellungen in .NET\-Konfigurationsdateien finden Sie unter [\<appSettings\>](http://go.microsoft.com/fwlink/?LinkId=95159) \(möglicherweise in englischer Sprache\).  
  
## Verwenden des Konfigurations\-Editors  
 Der [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht es Administratoren und Entwicklern, Konfigurationseinstellungen für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste mithilfe einer grafischen Benutzeroberfläche zu erstellen und zu bearbeiten.Mit diesem Tool können Sie die Einstellungen für Bindungen, Verhaltensweisen, Dienste und Diagnosen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwalten, ohne XML\-Dateien direkt bearbeiten zu müssen.  
  
## Bearbeiten von Konfigurationsdateien in Visual Studio  
 Klicken Sie zum Bearbeiten der Konfigurationsdatei eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstprojekts unter [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] im Projektmappen\-Explorermit der rechten Maustaste auf die entsprechende Datei, und wählen Sie im Kontextmenü die Option **WCF\-Konfiguration bearbeiten** aus.Das [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) wird gestartet.  
  
> [!NOTE]
>  Wenn Sie die Konfigurationsdatei eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Webdienstprojekts in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] bearbeiten möchten, indem Sie im **Projektmappen\-Explorer** mit der rechten Maustaste darauf klicken, beachten Sie, dass im Kontextmenü die Option **WCF\-Konfiguration bearbeiten** fehlt.Um dieses Problem zu umgehen, klicken Sie auf das Menü **Extras**, und wählen Sie **WCF\-Dienstkonfigurations\-Editor** aus.Danach können Sie mit der rechten Maustaste auf eine Konfigurationsdatei klicken und im Kontextmenü die Option **WCF\-Konfiguration bearbeiten** auswählen.  
  
## Siehe auch  
 [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)   
 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)