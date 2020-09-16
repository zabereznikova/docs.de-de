---
title: Konfigurieren der Anwendung
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 04ddce4755ce30b7d46c3bd54024af08361d96ad
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536080"
---
# <a name="configuring-your-application"></a>Konfigurieren der Anwendung
Windows Communication Foundation (WCF) verwendet das .NET-Konfigurationssystem und ermöglicht es Ihnen, Dienste sowohl im Computer-als auch im Anwendungsbereich zu konfigurieren.  
  
 Die von WCF definierten Konfigurationseinstellungen befinden sich in der `<system.serviceModel>` Abschnitts Gruppe. Weitere Informationen zum Konfigurieren eines WCF-Dienstanbieter finden Sie in den folgenden Themen:  
  
- [Konfigurieren von Diensten](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert. Weitere Informationen zu Anwendungseinstellungen in .NET-Konfigurationsdateien finden Sie unter [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)) .  
  
## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor  
 Mit dem WCF- [Konfigurations-Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) können Administratoren und Entwickler Konfigurationseinstellungen für WCF-Dienste mithilfe einer grafischen Benutzeroberfläche erstellen und ändern. Mit diesem Tool können Sie Einstellungen für WCF-Bindungen, Verhaltensweisen, Dienste und Diagnosen verwalten, ohne XML-Konfigurationsdateien direkt bearbeiten zu müssen.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Bearbeiten von Konfigurationsdateien in Visual Studio  
 Wenn Sie die Konfigurationsdatei eines WCF-Dienst Projekts in Visual Studio bearbeiten möchten, klicken Sie mit der rechten Maustaste auf **Projektmappen-Explorer** , und wählen Sie das Kontextmenü Element **WCF-Konfiguration bearbeiten** aus. Dadurch wird das [Tool für den Konfigurations-Editor (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)gestartet.  
  
> [!NOTE]
> Wenn Sie die Konfigurationsdatei eines WCF-Webdienst Projekts in Visual Studio bearbeiten, indem Sie in **Projektmappen-Explorer**mit der rechten Maustaste darauf klicken, beachten Sie, dass das Kontextmenü Element **WCF-Konfiguration bearbeiten** fehlt. Um dieses Problem zu umgehen, klicken Sie auf **das Menü Extras** , und wählen Sie **WCF-Dienst Konfigurations-Editor**aus. Anschließend können Sie mit der rechten Maustaste auf eine Konfigurationsdatei klicken und das Kontextmenü Element **WCF-Konfiguration bearbeiten** verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Configuration Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Konfigurieren von Diensten](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
