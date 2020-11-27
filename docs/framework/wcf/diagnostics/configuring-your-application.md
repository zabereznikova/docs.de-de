---
title: Konfigurieren der Anwendung
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e08e474be02ee11a6727df8b908b53ab1403f7f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294824"
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
> Wenn Sie die Konfigurationsdatei eines WCF-Webdienst Projekts in Visual Studio bearbeiten, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste darauf klicken, beachten Sie, dass das Kontextmenü Element **WCF-Konfiguration bearbeiten** fehlt. Um dieses Problem zu umgehen, klicken Sie auf **das Menü Extras** , und wählen Sie **WCF-Dienst Konfigurations-Editor** aus. Anschließend können Sie mit der rechten Maustaste auf eine Konfigurationsdatei klicken und das Kontextmenü Element **WCF-Konfiguration bearbeiten** verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Configuration Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Konfigurieren von Diensten](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
