---
title: Firefox-Add-Ons zur Unterstützung der .NET-Anwendungsbereitstellung
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: f05f5afa0c0a7ef858442bd98233865834b8b89b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Firefox-Add-Ons zur Unterstützung der .NET-Anwendungsbereitstellung
Aktivieren der Windows Presentation Foundation-Plug-In für Firefox und der .NET Framework-Assistent für Firefox (WPF) [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und ClickOnce-Anwendungen zur Bearbeitung von Mozilla Firefox-Browser.  
  
## <a name="wpf-plug-in-for-firefox"></a>WPF-Plug-In für Firefox  
 Ermöglicht das WPF-Plug-In für Firefox [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und Netzkabel ordnungsgemäß angeschlossen sind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien navigiert und auf der obersten Ebene oder in einem HTML-IFRAME in den Firefox-Browser ausgeführt werden. Ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ist eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung, die auf einem Webserver veröffentlicht und in gestartet werden kann, unterstützte Browser. Lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist eine nur-XAML-Datei, die navigiert und unterstützten Browsern, ähnlich wie eine XML-Datei angezeigt werden kann.  
  
 Die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-In für Firefox installiert ist, mit der [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Windows 7 enthält die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], aber nicht die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-In für Firefox. Kann nicht installiert werden die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-In für Firefox unter Windows 7.  
  
 Die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] schließt nicht die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-In für Firefox. Jedoch wenn beide die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] und [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] werden installiert, wird der WPF-Plug-In für Firefox mit installiert die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Aus diesem Grund [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] Anwendungen werden weiterhin ausgeführt werden, da der WPF-Host die richtige Version des Frameworks geladen werden. Weitere Informationen finden Sie unter [WPF-Host (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework-Assistent für Firefox  
 Der .NET Framework-Assistent für Firefox können eigenständige ClickOnce-Anwendungen über den Firefox-Browser ausgeführt. Der .NET Framework-Assistent für Firefox Funktionen identisch verwendet werden, wenn sie vor und nach den Firefox-Browser installiert ist. Bei der Firefox-Browser gestartet wird und die [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] ist installiert, Firefox findet und installiert die .NET Framework-Assistenten für Firefox. Benutzer können die .NET Framework-Assistenten für Firefox Folgendes konfigurieren:  
  
-   Fordert Sie vor dem Ausführen der ClickOnce-Anwendung.  
  
-   Melden Sie alle installierten Versionen von .NET Framework oder nur die neueste Version.  
  
 Der .NET Framework-Assistent für Firefox ist im Lieferumfang der [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Informationen zum Entfernen der .NET Framework-Assistent für Firefox finden Sie unter [Entfernen von der .NET Framework-Assistent für Firefox](http://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von WPF-Anwendungen](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)  
 [Übersicht über WPF-XAML-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)  
 [Erkennen einer Installation des WPF-Plug-Ins für Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
