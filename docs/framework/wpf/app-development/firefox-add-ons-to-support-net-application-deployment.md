---
title: Firefox-Add-Ons zur Unterstützung der .NET-Anwendungsbereitstellung
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 687f61bd3ec7d10c6aa66c20cd5eb58fcc56f18a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636366"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Firefox-Add-Ons zur Unterstützung der .NET-Anwendungsbereitstellung
Mit Windows Presentation Foundation dem WPF-Plug-in für Firefox und dem .NET Framework-Assistenten für Firefox können XAML-Browser Anwendungen (XBAPs), lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]und ClickOnce-Anwendungen mit dem Mozilla Firefox-Browser verwendet werden.  
  
## <a name="wpf-plug-in-for-firefox"></a>WPF-Plug-in für Firefox  
 Mit dem WPF-Plug-in für Firefox können XBAPs und lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateien auf der obersten Ebene oder in einem HTML-IFRAME im Firefox-Browser navigiert und ausgeführt werden. Eine XBAP ist eine WPF-Anwendung, die auf einem Webserver veröffentlicht und in unterstützten Browsern gestartet werden kann. Die lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist eine nur-XAML-Datei, die in einem unterstützten Browser navigiert und angezeigt werden kann, ähnlich wie eine XML-Datei.  
  
 Das WPF-Plug-in für Firefox wird mit dem .NET Framework 3,5 installiert. In Windows 7 ist der .NET Framework 3,5 enthalten, das WPF-Plug-in für Firefox ist jedoch nicht enthalten. Sie können das WPF-Plug-in für Firefox unter Windows 7 nicht installieren.  
  
 In .NET Framework 4 ist das WPF-Plug-in für Firefox nicht enthalten. Wenn jedoch die .NET Framework 3,5 und .NET Framework 4 installiert sind, wird das WPF-Plug-in für Firefox mit dem .NET Framework 3,5 installiert. Deshalb werden .NET Framework 4 Anwendungen weiterhin ausgeführt, da der WPF-Host die richtige Version des Frameworks lädt. Weitere Informationen finden Sie unter [WPF-Host (PresentationHost. exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework-Assistent für Firefox  
 Der .NET Framework-Assistent für Firefox ermöglicht das Ausführen eigenständiger ClickOnce-Anwendungen über den Firefox-Browser. Der .NET Framework-Assistent für Firefox funktioniert identisch, wenn er vor und nach dem Firefox-Browser installiert wird. Wenn der Firefox-Browser gestartet und der .NET Framework 3,5 SP1 installiert ist, wird der .NET Framework-Assistent für Firefox von Firefox gefunden und installiert. Benutzer können den .NET Framework-Assistenten für Firefox für folgende Aufgaben konfigurieren:  
  
- Eingabeaufforderung vor dem Ausführen der ClickOnce-Anwendung.  
  
- Melden Sie alle installierten Versionen des .NET Framework oder nur die neueste Version.  
  
 Der .NET Framework-Assistent für Firefox ist im .NET Framework 3,5 SP1 enthalten. Informationen zum Entfernen des .NET Framework-Assistenten für Firefox finden Sie unter Vorgehens [Weise beim Entfernen des .NET Framework-Assistenten für Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Siehe auch

- [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md)
- [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md)
- [Erkennen einer Installation des WPF-Plug-Ins für Firefox](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
