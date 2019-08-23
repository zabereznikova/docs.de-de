---
title: Bereitstellen von WPF-Anwendungen (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: cfb617fde514c93596d52b0ca70da39c6e5be301
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958648"
---
# <a name="deploying-a-wpf-application-wpf"></a>Bereitstellen von WPF-Anwendungen (WPF)
Nachdem Windows Presentation Foundation (WPF)-Anwendungen erstellt wurden, müssen Sie bereitgestellt werden. Windows und die .NET Framework umfassen mehrere Bereitstellungs Technologien. Die für die Bereitstellung einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung eingesetzte Technologie ist abhängig vom Anwendungstyp. Dieses Thema bietet eine kurze Übersicht über die einzelnen Bereitstellungstechnologien. Außerdem erfahren Sie, wie diese Bereitstellungstechnologien im Zusammenhang mit den Bereitstellungsvoraussetzungen für die verschiedenen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungstypen verwendet werden.  

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Bereitstellungstechnologien  
 Windows und die .NET Framework umfassen mehrere Bereitstellungs Technologien, einschließlich:  
  
- Bereitstellung mit XCopy  
  
- Bereitstellung mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]  
  
- ClickOnce-Bereitstellung:  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Bereitstellung mit XCopy  
 Bereitstellung mit XCopy bedeutet, dass mithilfe des XCopy-Befehlszeilenprogramms Dateien von einem Speicherort an einen anderen kopiert werden. Diese Art der Bereitstellung ist in den folgenden Fällen geeignet:  
  
- Es handelt sich um eine unabhängige, in sich geschlossene Anwendung. Der Client muss für die Ausführung nicht aktualisiert werden.  
  
- Anwendungsdateien müssen zwischen Speicherorten verschoben werden, zum Beispiel vom Ort der Erstellung (lokaler Datenträger, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)]-Dateifreigabe usw.) an den Ort der Veröffentlichung (Website, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)]-Dateifreigabe usw.).  
  
- Die Anwendung erfordert keine Shell-Integration (Verknüpfung im Startmenü, Symbol auf dem Desktop usw.).  
  
 XCopy eignet sich zwar für einfache Bereitstellungsszenarien, bietet jedoch zu wenige Funktionen für komplexe Bereitstellungen. Insbesondere fällt bei der Verwendung von XCopy häufig ein Mehraufwand für die Erstellung, Ausführung und Pflege von Skripten für die solide Verwaltung der Bereitstellung an. Außerdem werden bei XCopy Versionsverwaltung, Deinstallation und Rollback nicht unterstützt.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 Mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] können Anwendungen als eigenständige ausführbare Dateien gepackt werden, die auf einfache Weise an Clients verteilt und ausgeführt werden können. [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] Außerdem wird mit Windows installiert und ermöglicht die Integration mit dem Desktop, dem Startmenü und der Systemsteuerung.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] vereinfacht die Installation und Deinstallation von Anwendungen. Es bietet jedoch keine Versionsverwaltung, das heißt, die Möglichkeit sicherzustellen, dass die installierten Anwendungen immer auf dem neuesten Stand sind.  
  
 Weitere Informationen zu Windows Installer finden Sie unter [Windows Installer Bereitstellung](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 ClickOnce ermöglicht die Bereitstellung von Webanwendungen für nicht-Webanwendungen. Anwendungen werden auf Web- oder Dateiservern veröffentlicht und von dort bereitgestellt. Obwohl ClickOnce nicht den vollständigen Bereich von Client Funktionen [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]unterstützt, die von-installierten Anwendungen unterstützt werden, wird eine Teilmenge unterstützt, die Folgendes umfasst:  
  
- Einbindung in Startmenü und das Fenster für installierte Software in der Systemsteuerung  
  
- Versionsverwaltung, Rollback und Deinstallation  
  
- Online-Installationsmodus; dies bedeutet, dass die Anwendung immer vom Bereitstellungsort aus gestartet wird.  
  
- Automatische Aktualisierung, wenn neue Versionen freigegeben werden  
  
- Registrierung von Dateierweiterungen  
  
 Weitere Informationen zu ClickOnce finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Bereitstellen von WPF-Anwendungen  
 Die Bereitstellungsoptionen für eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung sind abhängig vom Typ der Anwendung. Im Rahmen der Bereitstellung gibt es bei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] drei Hauptanwendungstypen:  
  
- Eigenständige Anwendungen  
  
- Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendungen  
  
- [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Bereitstellen von eigenständigen Anwendungen  
 Eigenständige Anwendungen werden entweder mithilfe von ClickOnce [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]oder bereitgestellt. Bei beiden Methoden ist für die Ausführung der eigenständigen Anwendungen volle Vertrauenswürdigkeit erforderlich. Eigenständigen Anwendungen, die mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] bereitgestellt werden, wird die volle Vertrauenswürdigkeit automatisch gewährt. Eigenständige Anwendungen, die mithilfe von ClickOnce bereitgestellt werden, werden nicht automatisch voll vertrauenswürdig eingestuft. Stattdessen zeigt ClickOnce ein Dialogfeld mit einer Sicherheitswarnung an, das Benutzer vor der Installation einer eigenständigen Anwendung akzeptieren müssen. Bei Annahme der Warnung wird die eigenständige Anwendung installiert und erhält volle Vertrauenswürdigkeit. Wird die Warnung abgelehnt, wird die eigenständige Anwendung nicht installiert.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Bereitstellen von Markup-XAML-Anwendungen  
 Nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Markup-Seiten werden in der Regel auf Webservern veröffentlicht, wie z. b. HTML-Seiten und können mithilfe von Internet Explorer angezeigt werden. Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten werden mit einer teilweise vertrauenswürdigen Sandbox für die Sicherheit und Einschränkungen, die durch den Standardberechtigungssatz für die Internetzone definiert werden, ausgeführt. Dadurch wird eine entsprechende Sicherheits Sandbox für HTML-basierte Webanwendungen bereitgestellt.  
  
 Weitere Informationen zur Sicherheit von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen finden Sie unter [Sicherheit](../security-wpf.md).  
  
 Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten können mit XCopy oder [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] im lokalen Dateisystem installiert werden. Diese Seiten können mithilfe von Internet Explorer oder Windows-Explorer angezeigt werden.  
  
 Weitere Informationen über XAML finden Sie unter [Übersicht über XAML (WPF)](../advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Bereitstellen von XAML-Browseranwendungen  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sind kompilierte Anwendungen, bei denen die folgenden drei Dateien für die Bereitstellung erforderlich sind:  
  
- *ApplicationName*. exe: Die ausführbare Assemblyanwendungsdatei.  
  
- *ApplicationName*. XBAP: Das Bereitstellungs Manifest.  
  
- *ApplicationName*. exe. Manifest: Das Anwendungsmanifest.  
  
> [!NOTE]
> Weitere Informationen zu Anwendungs- und Bereitstellungsmanifesten finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
 Diese Dateien werden erzeugt, wenn eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] erstellt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie ein neues WPF-Browser](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))-Anwendungsprojekt. Wie nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] Seiten werden in der Regel auf einem Webserver veröffentlicht und mithilfe von Internet Explorer angezeigt.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s können mit einer beliebigen Bereitstellungstechnik auf Clients bereitgestellt werden. ClickOnce wird jedoch empfohlen, da es die folgenden Funktionen bietet:  
  
1. Automatische Updates, wenn eine neue Version veröffentlicht wird  
  
2. Berechtigungserweiterungen für die als voll vertrauenswürdig ausgeführte [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]  
  
 Standardmäßig veröffentlicht ClickOnce Anwendungsdateien mit der Erweiterung „.deploy“. Dies kann problematisch sein, kann jedoch deaktiviert werden. Weitere Informationen finden Sie unter [Probleme mit der Server- und Clientkonfiguration in ClickOnce-Bereitstellungen](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Weitere Informationen zur Bereitstellung von [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Installieren von .NET Framework  
 Zum Ausführen einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Anwendung muss das Microsoft .NET Framework auf dem Client installiert sein. Internet Explorer erkennt automatisch, ob Clients mit .NET Framework installiert werden [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , wenn im Browser gehostete Anwendungen angezeigt werden. Wenn die .NET Framework nicht installiert ist, werden Benutzer von Internet Explorer aufgefordert, Sie zu installieren.  
  
 Um zu ermitteln, ob die .NET Framework installiert ist, enthält Internet Explorer eine Bootstrapperanwendung, die als Fall Back-Multipurpose Internet Mail Extensions (MIME)-Handler für Inhalts Dateien mit den folgenden Erweiterungen registriert ist:. XAML,. XPS,. XBAP und. Application. Wenn Sie zu diesen Dateitypen navigieren und die .NET Framework nicht auf dem Client installiert ist, fordert die Boots Trapper-Anwendung die Berechtigung zur Installation an. Wenn keine Berechtigung bereitgestellt wird, wird weder der .NET Framework noch die Anwendung installiert.  
  
 Wenn die Berechtigung erteilt wird, lädt Internet Explorer die .NET Framework mithilfe von Microsoft Bits (Bits) herunter und installiert sie. Nach der erfolgreichen Installation des .NET Framework wird die ursprünglich angeforderte Datei in einem neuen Browserfenster geöffnet.  
  
 Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework und Anwendungen](../../deployment/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)
- [Sicherheit](../security-wpf.md)
