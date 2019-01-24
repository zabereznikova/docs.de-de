---
title: Firefox-Add-Ons zur Unterstützung der .NET-Anwendungsbereitstellung
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 31c6313adb24cd1a2cfca319ac5e243fcdf2b6a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583258"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Firefox-Add-Ons zur Unterstützung der .NET-Anwendungsbereitstellung
Aktivieren Sie das Windows Presentation Foundation-Plug-Ins für Firefox und .NET Framework Assistant für Firefox (WPF) [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und der ClickOnce-Anwendungen arbeiten mit den Mozilla Firefox-Browser.  
  
## <a name="wpf-plug-in-for-firefox"></a>WPF-Plug-Ins für Firefox  
 Die WPF-Plug-Ins für Firefox können [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] und loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] navigiert und führen Sie auf der obersten Ebene oder in einem HTML-IFRAME im Firefox-Browser von Dateien. Ein [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ist eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung, die auf einem Webserver veröffentlicht werden kann und die gestarteten unterstützte Browser. Lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist eine nur-XAML-Datei, die navigiert und unterstützten Browsern, ähnlich wie eine XML-Datei angezeigt werden kann.  
  
 Die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-Ins für Firefox installiert ist, mit der [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Windows 7 enthält die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], aber keine umfasst die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-Ins für Firefox. Sie können keine installieren die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-Ins für Firefox unter Windows 7.  
  
 Die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] schließt nicht die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Plug-Ins für Firefox. Jedoch sowohl die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] und [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] werden installiert, wird das WPF-Plug-Ins für Firefox mit installiert die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Aus diesem Grund [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] Anwendungen werden weiterhin ausgeführt werden, da der WPF-Host die richtige Version von Framework geladen werden. Weitere Informationen finden Sie unter [WPF-Host (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework-Assistent für Firefox  
 .NET Framework Assistant für Firefox können eigenständige ClickOnce-Anwendungen über den Firefox-Browser ausgeführt. .NET Framework Assistant für Firefox funktioniert genauso wie wenn es vor und nach dem Firefox-Browser installiert ist. Bei der Firefox-Browser gestartet wird und die [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] ist installiert, Firefox sucht und installiert .NET Framework Assistant für Firefox. Benutzer können .NET Framework Assistant für Firefox für Folgendes konfigurieren:  
  
-   Eingabeaufforderung vor dem Ausführen der ClickOnce-Anwendung.  
  
-   Melden Sie alle installierten Versionen von .NET Framework oder nur die neueste Version.  
  
 .NET Framework Assistant für Firefox ist im Lieferumfang der [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Informationen zum Entfernen von .NET Framework Assistant für Firefox, finden Sie unter [Gewusst wie: Entfernen von .NET Framework Assistant für Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Siehe auch
- [Bereitstellen von WPF-Anwendungen](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
- [Übersicht über WPF-XAML-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Erkennen einer Installation des WPF-Plug-Ins für Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
