---
title: Konfigurieren der Anwendung
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 39d8c73809b8c2695ccebb1d69d1c016fd2313d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584635"
---
# <a name="configuring-your-application"></a>Konfigurieren der Anwendung
Windows Communication Foundation (WCF) verwendet das Konfigurationssystem von .NET und ermöglicht es Ihnen, im Bereich Computer- und anwendungsspezifische Dienste zu konfigurieren.  
  
 Von WCF definierte Konfigurationseinstellungen befinden sich in der `<system.serviceModel>` Abschnittsgruppe. Weitere Informationen zum Konfigurieren eines WCF-Diensts finden Sie unter den folgenden Themen:  
  
-   [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert. Weitere Informationen zu Anwendungseinstellungen in .NET-Konfigurationsdateien finden Sie unter [ \<AppSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor  
 Die WCF [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) ermöglicht Administratoren und Entwicklern, Konfigurationseinstellungen für WCF-Dienste, die mithilfe einer grafischen Benutzeroberfläche zu erstellen. Mit diesem Tool können Sie Einstellungen für die WCF-Bindungen, Verhaltensweisen, Dienste und -Diagnose verwalten, ohne XML-Konfigurationsdateien direkt zu bearbeiten.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Bearbeiten von Konfigurationsdateien in Visual Studio  
 Zum Bearbeiten der Konfigurationsdatei von einem WCF-Dienstprojekt in Visual Studio mit der rechten Maustaste in **Projektmappen-Explorer** , und wählen Sie die **WCF-Konfiguration bearbeiten** Kontextmenüelement. Dadurch wird die [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Wenn Sie die Konfigurationsdatei eines WCF-Webdienst-Projekts in Visual Studio bearbeiten, indem Sie mit der rechten Maustaste in **Projektmappen-Explorer**, beachten Sie, dass die **WCF-Konfiguration bearbeiten** Kontextmenüelement ist nicht vorhanden. Dieses Problem umgehen, klicken Sie auf die **Tools** Menü, und wählen Sie **WCF-Dienstkonfigurations-Editor**. Danach können Sie mit der rechten Maustaste in einer Konfigurationsdatei und Verwenden der **WCF-Konfiguration bearbeiten** Kontextmenüelement.  
  
## <a name="see-also"></a>Siehe auch
- [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
