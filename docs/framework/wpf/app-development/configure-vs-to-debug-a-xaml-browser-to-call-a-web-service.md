---
title: 'Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: dcaabf9ecd47bc88095e92aa8ed28ad5f13fd1dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314372"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Führen Sie in einer teilweise vertrauenswürdigen Sicherheits-Sandbox, die auf das Internet Zone Berechtigungssatz beschränkt ist. Dieser Berechtigungssatz beschränkt Webdienstaufrufe nur Webdienste, die sich auf befinden die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Ursprungssite der Anwendung. Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debuggt wird von Visual Studio 2005, allerdings gilt dies nicht als Standort für die gleichen Ursprungs wie der Webdienst, das sie verweisen. Dieser bewirkt, dass Ausnahmen zur Codezugriffssicherheit ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen. Allerdings eine Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Projekt kann konfiguriert werden, um zu simulieren, müssen die gleiche Ursprungssite wie der Webdienst während des Debuggens ruft. Dadurch wird die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] zu sicher Aufrufen des Webdiensts ohne Sicherheitsausnahmen.

## <a name="configuring-visual-studio"></a>Konfigurieren von Visual Studio 2017
 So konfigurieren Sie Visual Studio 2005 zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , die einen Webdienst aufruft:

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.

3. In der **Startaktion** wählen Sie im Abschnitt **externes Programm starten** , und geben Sie Folgendes:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. In der **Startoptionen** Geben Sie Folgendes in die **Befehlszeilenargumente** Textfeld:

     `-debug`  *Dateiname*

     Die *Filename* Wert für die **-Debuggen** -Parameter ist der XBAP-Dateiname, z. B.:

     `-debug c:\example.xbap`

> [!NOTE]
>  Dies ist die Standardkonfiguration für Lösungen, die mit dem Visual Studio 2005 erstellten [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Projektvorlage.

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.

3. In der **Startoptionen** Abschnitt, fügen Sie die folgende Befehlszeilenparameter ein, um die **Befehlszeilenargumente** Textfeld:

     `-debugSecurityZoneURL` *URL*

     Die *URL* Wert für die **- DebugSecurityZoneURL** -Parameter ist der [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für den Speicherort an, die Sie als der Ursprungssite der Anwendung simulieren möchten.

 Betrachten Sie beispielsweise eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , die einen Webdienst verwendet, durch den folgenden [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Der Ursprungssite [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] für dieses Web-Dienst ist:

 `http://services.msdn.microsoft.com`

 Daher ist die vollständige **- DebugSecurityZoneURL** Befehlszeilenparameter und der Wert ist:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Siehe auch

- [WPF-Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
