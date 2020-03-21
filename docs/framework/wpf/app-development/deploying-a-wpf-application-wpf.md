---
title: Bereitstellen einer App
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 54d14503a0f65bb50f2dfb14d40af3b47d51589c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186309"
---
# <a name="deploy-a-wpf-application"></a>Bereitstellen einer WPF-Anwendung

Nachdem Windows Presentation Foundation (WPF)-Anwendungen erstellt wurden, müssen sie bereitgestellt werden. Windows und .NET Framework umfassen mehrere Bereitstellungstechnologien. Die Bereitstellungstechnologie, die zum Bereitstellen einer WPF-Anwendung verwendet wird, hängt vom Anwendungstyp ab. Dieses Thema bietet einen kurzen Überblick über die einzelnen Bereitstellungstechnologien und deren Verwendung in Verbindung mit den Bereitstellungsanforderungen der einzelnen WPF-Anwendungstypen.

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a>Bereitstellungstechnologien  
 Windows und .NET Framework umfassen mehrere Bereitstellungstechnologien, darunter:  
  
- Bereitstellung mit XCopy  
  
- Windows Installer-Bereitstellung.  
  
- ClickOnce-Bereitstellung.  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a>Bereitstellung mit XCopy  
 Bereitstellung mit XCopy bedeutet, dass mithilfe des XCopy-Befehlszeilenprogramms Dateien von einem Speicherort an einen anderen kopiert werden. Diese Art der Bereitstellung ist in den folgenden Fällen geeignet:  
  
- Es handelt sich um eine unabhängige, in sich geschlossene Anwendung. Der Client muss für die Ausführung nicht aktualisiert werden.  
  
- Anwendungsdateien müssen von einem Speicherort an einen anderen verschoben werden, z. B. von einem Buildspeicherort (lokaler Datenträger, UNC-Dateifreigabe usw.) an einen Veröffentlichungsort (Website, UNC-Dateifreigabe usw.).  
  
- Die Anwendung erfordert keine Shell-Integration (Verknüpfung im Startmenü, Symbol auf dem Desktop usw.).  
  
 XCopy eignet sich zwar für einfache Bereitstellungsszenarien, bietet jedoch zu wenige Funktionen für komplexe Bereitstellungen. Insbesondere fällt bei der Verwendung von XCopy häufig ein Mehraufwand für die Erstellung, Ausführung und Pflege von Skripten für die solide Verwaltung der Bereitstellung an. Außerdem werden bei XCopy Versionsverwaltung, Deinstallation und Rollback nicht unterstützt.  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a>Windows Installer  
 Mit Windows Installer können Anwendungen als eigenständige ausführbare Dateien verpackt werden, die einfach an Clients verteilt und ausgeführt werden können. Darüber hinaus wird Windows Installer mit Windows installiert und ermöglicht die Integration mit dem Desktop, dem Startmenü und dem Systemprogramm Programme.  
  
 Windows Installer vereinfacht die Installation und Deinstallation von Anwendungen, bietet jedoch keine Möglichkeiten, um sicherzustellen, dass installierte Anwendungen aus Versionssicht auf dem neuesten Stand gehalten werden.  
  
 Weitere Informationen zu Windows Installer finden Sie unter [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 ClickOnce ermöglicht die Anwendungsbereitstellung im Webstil für Nicht-Webanwendungen. Anwendungen werden auf Web- oder Dateiservern veröffentlicht und von dort bereitgestellt. Obwohl ClickOnce nicht die gesamte Palette von Clientfeatures unterstützt, die von Windows Installer-installierten Anwendungen verwendet werden, unterstützt es eine Teilmenge, die Folgendes enthält:  
  
- Einbindung in Startmenü und das Fenster für installierte Software in der Systemsteuerung  
  
- Versionsverwaltung, Rollback und Deinstallation  
  
- Online-Installationsmodus; dies bedeutet, dass die Anwendung immer vom Bereitstellungsort aus gestartet wird.  
  
- Automatische Aktualisierung, wenn neue Versionen freigegeben werden  
  
- Registrierung von Dateierweiterungen  
  
 Weitere Informationen zu ClickOnce finden Sie unter [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a>Bereitstellen von WPF-Anwendungen  
 Die Bereitstellungsoptionen für eine WPF-Anwendung hängen vom Anwendungstyp ab. Aus Sicht der Bereitstellung verfügt WPF über drei wichtige Anwendungstypen:  
  
- Eigenständige Anwendungen  
  
- Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendungen  
  
- XAML-Browseranwendungen (XBAPs).  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a>Bereitstellen von eigenständigen Anwendungen  
 Eigenständige Anwendungen werden entweder mit ClickOnce oder Windows Installer bereitgestellt. Bei beiden Methoden ist für die Ausführung der eigenständigen Anwendungen volle Vertrauenswürdigkeit erforderlich. Eigenständigen Anwendungen, die mit Windows Installer bereitgestellt werden, wird automatisch die volle Vertrauenswürdigkeit gewährt. Eigenständige Anwendungen, die mit ClickOnce bereitgestellt werden, erhalten nicht automatisch volle Vertrauenswürdigkeit. Stattdessen zeigt ClickOnce ein Sicherheitswarndialogfeld an, das Benutzer akzeptieren müssen, bevor eine eigenständige Anwendung installiert wird. Bei Annahme der Warnung wird die eigenständige Anwendung installiert und erhält volle Vertrauenswürdigkeit. Wird die Warnung abgelehnt, wird die eigenständige Anwendung nicht installiert.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a>Bereitstellen von Markup-XAML-Anwendungen  
 Nur Markupseiten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden in der Regel auf Webservern wie HTML-Seiten veröffentlicht und können mit Internet Explorer angezeigt werden. Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten werden mit einer teilweise vertrauenswürdigen Sandbox für die Sicherheit und Einschränkungen, die durch den Standardberechtigungssatz für die Internetzone definiert werden, ausgeführt. Dies stellt eine gleichwertige Sicherheits-Sandbox für HTML-basierte Webanwendungen bereit.  
  
 Weitere Informationen zur Sicherheit für WPF-Anwendungen finden Sie unter [Sicherheit](../security-wpf.md).  
  
 Nur Markupseiten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können mit XCopy oder Windows Installer auf dem lokalen Dateisystem installiert werden. Diese Seiten können mit Internet Explorer oder Windows Explorer angezeigt werden.  
  
 Weitere Informationen über XAML finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a>Bereitstellen von XAML-Browseranwendungen  
 XBAPs sind kompilierte Anwendungen, für die die folgenden drei Dateien bereitgestellt werden müssen:  
  
- *Anwendungsname*.exe: die ausführbare Assemblyanwendungsdatei  
  
- *Anwendungsname*.xbap: das Bereitstellungsmanifest  
  
- *Anwendungsname*.exe.manifest: das Anwendungsmanifest  
  
> [!NOTE]
> Weitere Informationen zu Anwendungs- und Bereitstellungsmanifesten finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
 Diese Dateien werden erstellt, wenn ein XBAP erstellt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Browseranwendungsprojekts](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). Wie Markupseiten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden XBAPs in der Regel auf einem Webserver veröffentlicht und mit Internet Explorer angezeigt.  
  
 XBAPs können mithilfe einer der Bereitstellungstechniken auf Clients bereitgestellt werden. ClickOnce wird jedoch empfohlen, da es die folgenden Funktionen bietet:  
  
1. Automatische Updates, wenn eine neue Version veröffentlicht wird  
  
2. Höhenberechtigungen für den XBAP, der mit voller Vertrauenswürdigkeit ausgeführt wird.  
  
 Standardmäßig veröffentlicht ClickOnce Anwendungsdateien mit der Erweiterung „.deploy“. Dies kann problematisch sein, kann jedoch deaktiviert werden. Weitere Informationen finden Sie unter [Probleme mit der Server- und Clientkonfiguration in ClickOnce-Bereitstellungen](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Weitere Informationen zum Bereitstellen von XAML-Browseranwendungen (XBAPs) finden Sie unter [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a>Installieren von .NET Framework  
 Zum Ausführen einer WPF-Anwendung muss Microsoft .NET Framework auf dem Client installiert sein. Internet Explorer erkennt automatisch, ob Clients mit .NET Framework installiert sind, wenn vom WPF-Browser gehostete Anwendungen angezeigt werden. Wenn .NET Framework nicht installiert ist, fordert Internet Explorer Benutzer auf, es zu installieren.  
  
 Um zu ermitteln, ob .NET Framework installiert ist, enthält Internet Explorer eine Bootstrapper-Anwendung, die als Fallback-MIME-Handler (Multipurpose Internet Mail Extensions) für Inhaltsdateien mit den folgenden Erweiterungen registriert ist: .xaml, .xps, .xbap , und .application. Wenn Sie zu diesen Dateitypen navigieren und .NET Framework nicht auf dem Client installiert ist, fordert die Bootstrapper-Anwendung die Berechtigung zum Installieren an. Wenn keine Berechtigung bereitgestellt wird, werden weder .NET Framework noch die Anwendung installiert.  
  
 Wenn die Berechtigung erteilt wird, lädt Und installiert Internet Explorer .NET Framework mithilfe des Microsoft Background Intelligent Transfer Service (BITS). Nach erfolgreicher Installation von .NET Framework wird die ursprünglich angeforderte Datei in einem neuen Browserfenster geöffnet.  
  
 Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework und Anwendungen](../../deployment/index.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)
- [Sicherheit](../security-wpf.md)
