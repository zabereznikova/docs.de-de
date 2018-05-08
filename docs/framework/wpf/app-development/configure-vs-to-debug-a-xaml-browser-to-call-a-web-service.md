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
ms.openlocfilehash: 948a730185650cb3449202503a049e9caff7c4bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Gewusst wie: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Führen Sie in einem Sandkasten Sicherheit bei teilweiser Vertrauenswürdigkeit, die auf das Internet Zone Berechtigungssatz beschränkt ist. Dieser Berechtigungssatz beschränkt Webdienstaufrufe, die nur auf Webdienste, die unter der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Ursprungssite der Anwendung. Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aus gedebuggt wird [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], obwohl er nicht die gleiche Ursprungssite haben, wie im Web service Verweise betrachtet wird. Diese Ursachen Sicherheitsausnahmen ausgelöst werden, wenn die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] versucht, den Webdienst aufzurufen. Allerdings eine [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] Projekt kann konfiguriert werden, um zu simulieren, die gleiche Ursprungssite wie der Webdienst aufgerufen wird, während des Debuggens. Dies ermöglicht die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] problemlos den Webdienst aufrufen, ohne Sicherheitsausnahmen.  
  
## <a name="configuring-visual-studio"></a>Konfigurieren von Visual Studio  
 So konfigurieren Sie [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] zum Debuggen einer [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] einen Webdienst aufruft:  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.  
  
3.  In der **Startaktion** Abschnitt **externes Programm starten** und geben Sie Folgendes ein:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  In der **Startoptionen** Abschnitt, geben Sie Folgendes in die **Befehlszeilenargumente** Textfeld:  
  
     `-debug`  *Dateiname*  
  
     Die *Filename* Wert für die **-Debuggen** Parameter ist der XBAP-Dateiname, z. B.:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Dies ist die Standardkonfiguration für Projektmappen, die mit erstellt wurden, die [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] -Projektvorlage.  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  In der **Projekt-Designer**, klicken Sie auf die **Debuggen** Registerkarte.  
  
3.  In der **Startoptionen** Abschnitt, fügen Sie die folgenden Befehlszeilenparameter, die **Befehlszeilenargumente** Textfeld:  
  
     `-debugSecurityZoneURL` *URL*  
  
     Die *URL* Wert für die **- DebugSecurityZoneURL** Parameter ist der [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] für den Speicherort, den Sie als der Ursprungssite Ihrer Anwendung simulieren möchten.  
  
 Betrachten Sie als Beispiel eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] verwendet, die einen Webdienst mit den folgenden [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 Der Ursprungssite [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] für diese Web-Dienst ist:  
  
 `http://services.msdn.microsoft.com`  
  
 Infolgedessen ist die vollständige **- DebugSecurityZoneURL** Befehlszeilenparameter und Wert ist:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a>Siehe auch  
 [WPF-Host (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
