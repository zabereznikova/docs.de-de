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
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958689"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]Ausführung innerhalb einer teilweise vertrauenswürdigen Sicherheits Sandbox, die auf den Berechtigungs Satz für die Internet Zone beschränkt ist. Dieser Berechtigungs Satz schränkt Webdienst Aufrufe nur auf Webdienste ein, die sich [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] auf der Ursprungs Site der Anwendung befinden. Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aus Visual Studio 2005 entfernt wird, wird jedoch nicht die gleiche Ursprungs Site wie der Webdienst betrachtet, auf den er verweist. Dies bewirkt, dass Sicherheits Ausnahmen ausgelöst werden, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] wenn der versucht, den Webdienst aufzurufen. Ein Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] -Projekt kann jedoch so konfiguriert werden, dass es die gleiche Ursprungs Site wie der Webdienst simuliert, der beim Debuggen aufgerufen wird. Dadurch kann der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] den Webdienst sicher aufzurufen, ohne Sicherheits Ausnahmen zu verursachen.

## <a name="configuring-visual-studio"></a>Konfigurieren von Visual Studio 2017
 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] So konfigurieren Sie Visual Studio 2005 zum Debuggen von, das einen Webdienst aufruft:

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .

3. Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten** aus, und geben Sie Folgendes ein:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. Geben Sie im Abschnitt **Start Optionen** Folgendes in das Textfeld **Befehlszeilenargumente** ein:

     `-debug`  *Einfügen*

     Der *Dateiname* des Parameters " **-Debug** " ist der Dateiname ". XBAP". Zum Beispiel:

     `-debug c:\example.xbap`

> [!NOTE]
> Dies ist die Standardkonfiguration für Projektmappen, die mit der Visual Studio [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 2005-Projektvorlage erstellt werden.

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .

3. Fügen Sie im Abschnitt **Start Optionen** den folgenden Befehlszeilenparameter in das Textfeld **Befehlszeilenargumente** ein:

     `-debugSecurityZoneURL` *URL*

     Der *URL* -Wert für den **-DebugSecurityZoneURL-** Parameter [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] ist der für den Speicherort, den Sie als Ursprungs Site der Anwendung simulieren möchten.

 Angenommen, [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] Sie verwenden einen Webdienst mit folgendem [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Die Ursprungs [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] Site für diesen Webdienst lautet:

 `http://services.msdn.microsoft.com`

 Folglich lautet der Befehlszeilenparameter Complete **-Debug securityzoneurl** und der Wert:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Siehe auch

- [WPF-Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
