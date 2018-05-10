---
title: Konfigurieren der Anwendung
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 1844c20ef961f191fb667e31d548518b193a7134
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="configuring-your-application"></a>Konfigurieren der Anwendung
Windows Communication Foundation (WCF) verwendet das Konfigurationssystem .NET und können Sie im Bereich Computer- und anwendungsspezifische Dienste zu konfigurieren.  
  
 Von WCF definierte Konfigurationseinstellungen befinden sich der `<system.serviceModel>` Abschnittsgruppe. Weitere Informationen zum Konfigurieren eines WCF-Diensts finden Sie unter den folgenden Themen:  
  
-   [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert. Weitere Informationen zu Anwendungseinstellungen in Konfigurationsdateien .NET finden Sie unter [ \<"appSettings" >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor  
 Die WCF[Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) ermöglicht Administratoren und Entwicklern, Konfigurationseinstellungen für WCF-Dienste, die mithilfe einer grafischen Benutzeroberfläche zu erstellen. Mit diesem Tool können Sie Einstellungen für den WCF-Bindungen, Verhaltensweisen, Dienste und -Diagnose verwalten, ohne die XML-Dateien direkt bearbeiten.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Bearbeiten von Konfigurationsdateien in Visual Studio  
 Zum Bearbeiten der Konfigurationsdatei von einem WCF-Dienstprojekt in Visual Studio mit der rechten Maustaste klicken Sie auf diese in **Projektmappen-Explorer** , und wählen Sie die **WCF-Konfiguration bearbeiten** Kontextmenüelement. Dadurch wird die [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Wenn Sie die Konfigurationsdatei eines WCF-Webdienst-Projekts in Visual Studio bearbeiten, indem Sie mit der rechten Maustaste in **Projektmappen-Explorer**, beachten Sie, dass die **WCF-Konfiguration bearbeiten** Kontextmenüelement ist nicht vorhanden. Zur Umgehung dieses Problem, klicken Sie auf die **Tools** Menü, und wählen Sie **WCF-Dienstkonfigurations-Editor**. Danach können Sie mit der rechten Maustaste einer Konfigurationsdatei und die **WCF-Konfiguration bearbeiten** Kontextmenüelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
