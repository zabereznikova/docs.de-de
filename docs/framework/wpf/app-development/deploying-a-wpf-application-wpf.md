---
title: Bereitstellen von WPF-Anwendungen (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 0ffd4fb05a5a409d74f8a9401a5fb021db0cd99b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320651"
---
# <a name="deploying-a-wpf-application-wpf"></a>Bereitstellen von WPF-Anwendungen (WPF)
Nachdem Windows Presentation Foundation (WPF)-Anwendungen erstellt werden, müssen sie bereitgestellt werden. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und das .NET Framework bieten verschiedene bereitstellungstechnologien. Die für die Bereitstellung einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung eingesetzte Technologie ist abhängig vom Anwendungstyp. Dieses Thema bietet eine kurze Übersicht über die einzelnen Bereitstellungstechnologien. Außerdem erfahren Sie, wie diese Bereitstellungstechnologien im Zusammenhang mit den Bereitstellungsvoraussetzungen für die verschiedenen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungstypen verwendet werden.  

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Bereitstellungstechnologien  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und das .NET Framework bieten verschiedene bereitstellungstechnologien, einschließlich:  
  
-   Bereitstellung mit XCopy  
  
-   [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] die Bereitstellung.  
  
-   [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] die Bereitstellung.  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Bereitstellung mit XCopy  
 Bereitstellung mit XCopy bedeutet, dass mithilfe des XCopy-Befehlszeilenprogramms Dateien von einem Speicherort an einen anderen kopiert werden. Diese Art der Bereitstellung ist in den folgenden Fällen geeignet:  
  
-   Es handelt sich um eine unabhängige, in sich geschlossene Anwendung. Der Client muss für die Ausführung nicht aktualisiert werden.  
  
-   Anwendungsdateien müssen zwischen Speicherorten verschoben werden, zum Beispiel vom Ort der Erstellung (lokaler Datenträger, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)]-Dateifreigabe usw.) an den Ort der Veröffentlichung (Website, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)]-Dateifreigabe usw.).  
  
-   Die Anwendung erfordert keine Shell-Integration (Verknüpfung im Startmenü, Symbol auf dem Desktop usw.).  
  
 XCopy eignet sich zwar für einfache Bereitstellungsszenarien, bietet jedoch zu wenige Funktionen für komplexe Bereitstellungen. Insbesondere fällt bei der Verwendung von XCopy häufig ein Mehraufwand für die Erstellung, Ausführung und Pflege von Skripten für die solide Verwaltung der Bereitstellung an. Außerdem werden bei XCopy Versionsverwaltung, Deinstallation und Rollback nicht unterstützt.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] ermöglicht Anwendungen, die als eigenständige ausführbare Dateien gepackt werden, die leicht an Clients verteilt und ausgeführt werden können. Darüber hinaus wird [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] mit [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] installiert und ermöglicht die Einbindung in Desktop, Startmenü und das Fenster für installierte Software in der Systemsteuerung.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] vereinfacht die Installation und Deinstallation von Anwendungen, aber es bietet keine Möglichkeit sicherzustellen, dass die installierte Anwendungen auf, die vom Standpunkt der versionsverwaltung dem neuesten Stand gehalten werden.  
  
 Weitere Informationen zu Windows Installer finden Sie unter [Windows Installer-Bereitstellung](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] ermöglicht die Bereitstellung von Web-ähnliches Anwendung für nicht-Webanwendungen. Anwendungen werden auf Web- oder Dateiservern veröffentlicht und von dort bereitgestellt. [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] unterstützt zwar nicht alle Clientfeatures, die von den mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] installierten Anwendungen bereitgestellt werden, es steht jedoch eine Teilmenge dieser Features zur Verfügung. Hierzu gehören die folgenden Funktionen:  
  
-   Einbindung in Startmenü und das Fenster für installierte Software in der Systemsteuerung  
  
-   Versionsverwaltung, Rollback und Deinstallation  
  
-   Online-Installationsmodus; dies bedeutet, dass die Anwendung immer vom Bereitstellungsort aus gestartet wird.  
  
-   Automatische Aktualisierung, wenn neue Versionen freigegeben werden  
  
-   Registrierung von Dateierweiterungen  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Bereitstellen von WPF-Anwendungen  
 Die Bereitstellungsoptionen für eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung sind abhängig vom Typ der Anwendung. Im Rahmen der Bereitstellung gibt es bei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] drei Hauptanwendungstypen:  
  
-   Eigenständige Anwendungen  
  
-   Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendungen  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]sein.  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Bereitstellen von eigenständigen Anwendungen  
 Eigenständige Anwendungen werden mit [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] oder mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] bereitgestellt. Bei beiden Methoden ist für die Ausführung der eigenständigen Anwendungen volle Vertrauenswürdigkeit erforderlich. Eigenständigen Anwendungen, die mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] bereitgestellt werden, wird die volle Vertrauenswürdigkeit automatisch gewährt. Bei der Bereitstellung mit [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] wird die volle Vertrauenswürdigkeit jedoch nicht automatisch gewährt. [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] zeigt stattdessen eine Sicherheitswarnung an, die akzeptiert werden muss, bevor eine eigenständige Anwendung installiert wird. Bei Annahme der Warnung wird die eigenständige Anwendung installiert und erhält volle Vertrauenswürdigkeit. Wird die Warnung abgelehnt, wird die eigenständige Anwendung nicht installiert.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Bereitstellen von Markup-XAML-Anwendungen  
 Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten werden normalerweise wie [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]-Seiten auf Webservern veröffentlicht und können mit [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] angezeigt werden. Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten werden mit einer teilweise vertrauenswürdigen Sandbox für die Sicherheit und Einschränkungen, die durch den Standardberechtigungssatz für die Internetzone definiert werden, ausgeführt. Dies stellt eine Sandbox für die Sicherheit bereit, die der von [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]-basierten Webanwendungen entspricht.  
  
 Weitere Informationen zur Sicherheit von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen finden Sie unter [Sicherheit](../security-wpf.md).  
  
 Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten können mit XCopy oder [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] im lokalen Dateisystem installiert werden. Diese Seiten können angezeigt werden, mithilfe von [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] oder Windows-Explorer.  
  
 Weitere Informationen über XAML finden Sie unter [Übersicht über XAML (WPF)](../advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Bereitstellen von XAML-Browseranwendungen  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sind kompilierte Anwendungen, die die folgenden drei Dateien bereitgestellt werden müssen:  
  
-   *ApplicationName*.exe: Die ausführbare Assembly-Anwendungsdatei.  
  
-   *ApplicationName*.xbap: Das Bereitstellungsmanifest.  
  
-   *ApplicationName*.exe.manifest: Das Anwendungsmanifest.  
  
> [!NOTE]
>  Weitere Informationen zu Anwendungs- und Bereitstellungsmanifesten finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
 Diese Dateien werden erzeugt, wenn eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] erstellt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen ein neues WPF-Browseranwendungsprojekts](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). Wie Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten werden [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s normalerweise auf einem Webserver veröffentlicht und mit [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] angezeigt.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] kann von Clients mithilfe eines der Bereitstellungsverfahren bereitgestellt werden. [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] wird jedoch empfohlen, da es die folgenden Funktionen bietet:  
  
1. Automatische Updates, wenn eine neue Version veröffentlicht wird  
  
2. Berechtigungserweiterungen für die als voll vertrauenswürdig ausgeführte [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]  
  
 Standardmäßig veröffentlicht ClickOnce Anwendungsdateien mit der Erweiterung „.deploy“. Dies kann problematisch sein, kann jedoch deaktiviert werden. Weitere Informationen finden Sie unter [Probleme mit der Server- und Clientkonfiguration in ClickOnce-Bereitstellungen](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Weitere Informationen zur Bereitstellung von [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Installieren von .NET Framework  
 Zum Ausführen einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung ist, muss Microsoft .NET Framework auf dem Client installiert werden. [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] erkennt automatisch, ob Clients mit dem .NET Framework installiert sind beim [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] im Browser gehostete Anwendungen angezeigt werden. Wenn .NET Framework nicht installiert ist, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] werden Benutzer zur Installation aufgefordert.  
  
 Um festzustellen, ob .NET Framework installiert ist, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] enthält eine Bootstrapper-Anwendung, die als Fallback-registriert ist [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] Handler für Inhaltsdateien mit den folgenden Erweiterungen: .xaml, .xps, .xbap und .application. Wenn Sie diese Dateitypen öffnen, und .NET Framework nicht auf dem Client installiert ist, fordert die Bootstrapper-Anwendung die Berechtigung zum Installieren. Wenn die Berechtigung nicht angegeben ist, wird weder die Anwendung als auch .NET Framework installiert.  
  
 Wenn die Berechtigung erteilt wird, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] heruntergeladen und installiert die .NET Framework mit der [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]. Nach der erfolgreichen Installation von .NET Framework wird die ursprünglich angeforderte Datei in einem neuen Browserfenster geöffnet.  
  
 Automatische Erkennung von .NET Framework steht auf [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)], und [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] Clients mit [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] oder höher installiert.  
  
 Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework und Anwendungen](../../deployment/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)
- [Sicherheit](../security-wpf.md)
