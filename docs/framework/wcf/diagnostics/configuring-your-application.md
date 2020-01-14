---
title: Konfigurieren der Anwendung
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 6fc33e7b114bb78f823575a2b456d601ae75db94
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937642"
---
# <a name="configuring-your-application"></a>Konfigurieren der Anwendung
Windows Communication Foundation (WCF) verwendet das .NET-Konfigurationssystem und ermöglicht es Ihnen, Dienste sowohl im Computer-als auch im Anwendungsbereich zu konfigurieren.  
  
 Die von WCF definierten Konfigurationseinstellungen befinden sich in der `<system.serviceModel>` Abschnitts Gruppe. Weitere Informationen zum Konfigurieren eines WCF-Dienstanbieter finden Sie in den folgenden Themen:  
  
- [Konfigurieren von Diensten](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Anwendungsdefinierte Konfigurationseinstellungen sind in der `<appSettings>`-Abschnittsgruppe definiert. Weitere Informationen zu Anwendungseinstellungen in .NET-Konfigurationsdateien finden Sie unter [\<appSettings >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).  
  
## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor  
 Das WCF- [Konfigurations-Editor-Tool (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md) ermöglicht es Administratoren und Entwicklern, Konfigurationseinstellungen für WCF-Dienste mithilfe einer grafischen Benutzeroberfläche zu erstellen und zu ändern. Mit diesem Tool können Sie Einstellungen für WCF-Bindungen, Verhaltensweisen, Dienste und Diagnosen verwalten, ohne XML-Konfigurationsdateien direkt bearbeiten zu müssen.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Bearbeiten von Konfigurationsdateien in Visual Studio  
 Wenn Sie die Konfigurationsdatei eines WCF-Dienst Projekts in Visual Studio bearbeiten möchten, klicken Sie mit der rechten Maustaste auf **Projektmappen-Explorer** , und wählen Sie das Kontextmenü Element **WCF-Konfiguration bearbeiten** aus. Dadurch wird das [Konfigurations-Editor-Tool (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md)gestartet.  
  
> [!NOTE]
> Wenn Sie die Konfigurationsdatei eines WCF-Webdienst Projekts in Visual Studio bearbeiten, indem Sie in **Projektmappen-Explorer**mit der rechten Maustaste darauf klicken, beachten Sie, dass das Kontextmenü Element **WCF-Konfiguration bearbeiten** fehlt. Um dieses Problem zu umgehen, klicken Sie auf **das Menü Extras** , und wählen Sie **WCF-Dienst Konfigurations-Editor**aus. Anschließend können Sie mit der rechten Maustaste auf eine Konfigurationsdatei klicken und das Kontextmenü Element **WCF-Konfiguration bearbeiten** verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Configuration Editor-Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Konfigurieren von Diensten](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
