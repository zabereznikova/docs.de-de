---
title: WPF-Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 3f51f274a4cba77f6bc7b62d6e31d476625072a5
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796896"
---
# <a name="wpf-host-presentationhostexe"></a>WPF-Host (PresentationHost.exe)
Windows Presentation Foundation (WPF)-Host (PresentationHost. exe) ist die Anwendung, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mit der Anwendungen in kompatiblen Browsern (einschließlich [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] und höher) gehostet werden können. Standardmäßig wird der WPF-Host (Windows Presentation Foundation) als Shell und [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] Handler für im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Inhalte registriert, einschließlich:  
  
- Loose (nicht kompilierte) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien (.xaml)  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap)  
  
 Für Dateien dieser Typen Windows Presentation Foundation (WPF)-Host:  
  
- Hiermit wird der registrierte HTML-Handler zum Hosten des Windows Presentation Foundation-Inhalts (WPF) gestartet.  
  
- Lädt die richtigen Versionen der erforderlichen Common Language Runtime-Assemblys (CLR) und Windows Presentation Foundation (WPF).  
  
- Überprüfen, ob die entsprechenden Berechtigungsstufen für die Bereitstellungszone aktiv sind.  
  
 In diesem Thema werden die Befehlszeilenparameter beschrieben, die mit „PresentationHost.exe“ verwendet werden können.  
  
## <a name="usage"></a>Verwendung  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|filename|Der Pfad der zu aktivierenden Datei. Es kann sich auch um einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] handeln.|  
|-Debug|Beim Aktivieren einer Anwendung wird diese nicht in den Speicher übernommen oder daraus ausgeführt. Dies funktioniert nur, wenn eine lokale Datei aktiviert wird.|  
|-debugSecurityZoneURL \<URL>|Wird mit einem [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]-Wert verwendet, um für „PresentationHost.exe“ anzugeben, dass eine Anwendung so gedebuggt werden sollte, als ob sie von der angegebenen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] bereitgestellt werden sollte. Dadurch werden die Bereitstellungszone und die Ursprungssite bestimmt.|  
|-embedding|Wird von OLE benötigt. Wenn der Parameter `-event` oder `-debug` angegeben wird, ist es nicht nötig, den `-embedding`-Parameter anzugeben, da dieser Parameter intern festgelegt wird.|  
|-event \<Ereignisname>|Öffnen Sie das Ereignis mit diesem Namen, und signalisieren Sie es, wenn „PresentationHost.exe“ initialisiert wird und bereit ist, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Inhalte zu hosten. „PresentationHost.exe“ wird beendet, wenn beim Öffnen des Ereignisses ein Fehler auftritt, z. B. wenn es noch nicht erstellt wurde.|  
|-launchApplication \<URL>|Hiermit wird eine eigenständige ClickOnce-Anwendung aus der angegebenen URL gestartet. [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]- und WinInet-Sicherheitsrichtlinie für .NET-Anwendungen werden angewendet.|  
  
## <a name="scenarios"></a>Szenarien  
  
### <a name="shell-handler"></a>Shell-Handler  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>MIME-Handler  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Debuggen in Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>Visual Studio: Debuggen in einer Zone  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheit](../security-wpf.md)
