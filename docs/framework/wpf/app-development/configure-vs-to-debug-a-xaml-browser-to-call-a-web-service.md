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
ms.openlocfilehash: 8ec278f2bc66d9b40786123af684f6468b6a9d83
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005671"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Vorgehensweise: Konfigurieren von Visual Studio zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] wird in einer teilweise vertrauenswürdigen Sicherheits Sandbox ausgeführt, die auf den Berechtigungs Satz für die Internet Zone beschränkt ist. Dieser Berechtigungs Satz schränkt Webdienst Aufrufe nur auf Webdienste ein, die sich auf der Ursprungs Site der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Anwendung befinden. Wenn eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aus Visual Studio 2005 deentschlbelt wird, wird Sie nicht als dieselbe Ursprungs Site wie der Webdienst betrachtet, auf den Sie verweist. Dies bewirkt, dass Sicherheits Ausnahmen ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen. Ein Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]-Projekt kann jedoch so konfiguriert werden, dass es die gleiche Ursprungs Site wie der Webdienst simuliert, der beim Debuggen aufgerufen wird. Dies ermöglicht es dem [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], den Webdienst sicher aufzurufen, ohne Sicherheits Ausnahmen zu verursachen.

## <a name="configuring-visual-studio"></a>Konfigurieren von Visual Studio 2017
 So konfigurieren Sie Visual Studio 2005 zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], die einen Webdienst aufruft:

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .

3. Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten** aus, und geben Sie Folgendes ein:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. Geben Sie im Abschnitt **Start Optionen** Folgendes in das Textfeld **Befehlszeilenargumente** ein:

     *Dateiname* von `-debug`

     Der *Dateiname* des Parameters "-Debug" ist der **Dateiname** ". XBAP". Zum Beispiel:

     `-debug c:\example.xbap`

> [!NOTE]
> Dies ist die Standardkonfiguration für Projektmappen, die mit der Projektvorlage Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] erstellt werden.

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .

3. Fügen Sie im Abschnitt **Start Optionen** den folgenden Befehlszeilenparameter in das Textfeld **Befehlszeilenargumente** ein:

     `-debugSecurityZoneURL` *URL*

     Der *URL* -Wert für den **-DebugSecurityZoneURL-** Parameter ist der [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für den Speicherort, den Sie als Ursprungs Site der Anwendung simulieren möchten.

 Angenommen, ein [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] verwendet einen Webdienst mit der folgenden URL:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Die URL für den Ursprungs Standort für diesen Webdienst lautet:

 `http://services.msdn.microsoft.com`

 Folglich lautet der Befehlszeilenparameter Complete **-Debug securityzoneurl** und der Wert:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Siehe auch

- [WPF-Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
