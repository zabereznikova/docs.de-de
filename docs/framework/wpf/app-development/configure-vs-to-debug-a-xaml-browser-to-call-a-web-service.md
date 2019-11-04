---
title: 'Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460900"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen
XAML-Browser Anwendungen (XBAPs) werden in einer teilweise vertrauenswürdigen Sicherheits Sandbox ausgeführt, die auf den Berechtigungs Satz für die Internet Zone beschränkt ist. Dieser Berechtigungs Satz schränkt Webdienst Aufrufe nur auf Webdienste ein, die sich auf der Ursprungs Site der XBAP-Anwendung befinden. Wenn eine XBAP aus Visual Studio 2005 deentschlbelt wird, wird Sie jedoch nicht als dieselbe Ursprungs Site wie der Webdienst betrachtet, auf den Sie verweist. Dies bewirkt, dass Sicherheits Ausnahmen ausgelöst werden, wenn die XBAP versucht, den Webdienst aufzurufen. Ein Projekt mit einer Visual Studio 2005 XAML-Browser Anwendung (WPF) kann jedoch so konfiguriert werden, dass es dieselbe Ursprungs Site wie der Webdienst simuliert, der während des Debuggens aufgerufen wird. Dies ermöglicht es der XBAP, den Webdienst sicher aufzurufen, ohne Sicherheits Ausnahmen zu verursachen.

## <a name="configuring-visual-studio"></a>Konfigurieren von Visual Studio 2017
 So konfigurieren Sie Visual Studio 2005 zum Debuggen einer XBAP, die einen Webdienst aufruft:

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .

3. Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten** aus, und geben Sie Folgendes ein:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. Geben Sie im Abschnitt **Start Optionen** Folgendes in das Textfeld **Befehlszeilenargumente** ein:

     *Dateiname* von `-debug`

     Der *Dateiname* des Parameters "-Debug" ist der **Dateiname** ". XBAP". Zum Beispiel:

     `-debug c:\example.xbap`

> [!NOTE]
> Dies ist die Standardkonfiguration für Projektmappen, die mit der Projektvorlage "Visual Studio 2005 XAML-Browser Anwendung (WPF)" erstellt werden.

1. Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie im **Projekt-Designer**auf die Registerkarte **Debuggen** .

3. Fügen Sie im Abschnitt **Start Optionen** den folgenden Befehlszeilenparameter in das Textfeld **Befehlszeilenargumente** ein:

     `-debugSecurityZoneURL` *URL*

     Der *URL* -Wert für den **-DebugSecurityZoneURL-** Parameter ist die URL für den Speicherort, den Sie als Ursprungs Site der Anwendung simulieren möchten.

 Stellen Sie sich als Beispiel eine XAML-Browser Anwendung (XBAP) vor, die einen Webdienst mit der folgenden URL verwendet:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Die URL für den Ursprungs Standort für diesen Webdienst lautet:

 `http://services.msdn.microsoft.com`

 Folglich lautet der Befehlszeilenparameter Complete **-Debug securityzoneurl** und der Wert:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Siehe auch

- [WPF-Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
