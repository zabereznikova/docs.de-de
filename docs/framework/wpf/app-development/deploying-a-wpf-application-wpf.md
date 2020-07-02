---
title: Bereitstellen einer App
description: Erkunden Sie die Bereitstellungs Technologien, die Windows und die .NET Framework für Windows Presentation Foundation (WPF)-Anwendungen verwenden.
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 62904ccd47800c8340d68c223e50688902170063
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619298"
---
# <a name="deploy-a-wpf-application"></a>Bereitstellen einer WPF-Anwendung

Nachdem Windows Presentation Foundation (WPF)-Anwendungen erstellt wurden, müssen Sie bereitgestellt werden. Windows und die .NET Framework umfassen mehrere Bereitstellungs Technologien. Die Bereitstellungs Technologie, die für die Bereitstellung einer WPF-Anwendung verwendet wird, hängt vom Anwendungstyp ab. Dieses Thema enthält eine kurze Übersicht über die einzelnen Bereitstellungs Technologien und deren Verwendung in Verbindung mit den Bereitstellungs Anforderungen der einzelnen WPF-Anwendungstyp.

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a>Bereitstellungstechnologien  
 Windows und die .NET Framework umfassen mehrere Bereitstellungs Technologien, einschließlich:  
  
- Bereitstellung mit XCopy  
  
- Windows Installer Bereitstellung.  
  
- ClickOnce-Bereitstellung.  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a>Bereitstellung mit XCopy  
 Bereitstellung mit XCopy bedeutet, dass mithilfe des XCopy-Befehlszeilenprogramms Dateien von einem Speicherort an einen anderen kopiert werden. Diese Art der Bereitstellung ist in den folgenden Fällen geeignet:  
  
- Es handelt sich um eine unabhängige, in sich geschlossene Anwendung. Der Client muss für die Ausführung nicht aktualisiert werden.  
  
- Anwendungs Dateien müssen von einem Speicherort zu einem anderen verschoben werden, z. b. von einem Buildspeicherort (lokaler Datenträger, UNC-Dateifreigabe usw.) an einen Veröffentlichungsort (Website, UNC-Dateifreigabe usw.).  
  
- Die Anwendung erfordert keine Shell-Integration (Verknüpfung im Startmenü, Symbol auf dem Desktop usw.).  
  
 XCopy eignet sich zwar für einfache Bereitstellungsszenarien, bietet jedoch zu wenige Funktionen für komplexe Bereitstellungen. Insbesondere fällt bei der Verwendung von XCopy häufig ein Mehraufwand für die Erstellung, Ausführung und Pflege von Skripten für die solide Verwaltung der Bereitstellung an. Außerdem werden bei XCopy Versionsverwaltung, Deinstallation und Rollback nicht unterstützt.  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a>Windows Installer  
 Mit Windows Installer können Anwendungen als eigenständige ausführbare Dateien gepackt werden, die auf einfache Weise an Clients verteilt und ausgeführt werden können. Außerdem wird Windows Installer mit Windows installiert und ermöglicht die Integration mit dem Desktop, dem Startmenü und der Systemsteuerung.  
  
 Windows Installer vereinfacht die Installation und die Installation von Anwendungen, stellt jedoch keine Funktionen bereit, um sicherzustellen, dass installierte Anwendungen von der Versionskontrolle aus auf dem neuesten Stand gehalten werden.  
  
 Weitere Informationen zu Windows Installer finden Sie unter [Windows Installer Bereitstellung](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a>ClickOnce-Bereitstellung  
 ClickOnce ermöglicht die Bereitstellung von Webanwendungen für nicht-Webanwendungen. Anwendungen werden auf Web- oder Dateiservern veröffentlicht und von dort bereitgestellt. Obwohl ClickOnce nicht den vollständigen Bereich von Client Funktionen unterstützt, die von Windows Installer installierten Anwendungen unterstützt werden, wird eine Teilmenge unterstützt, die Folgendes umfasst:  
  
- Einbindung in Startmenü und das Fenster für installierte Software in der Systemsteuerung  
  
- Versionsverwaltung, Rollback und Deinstallation  
  
- Online-Installationsmodus; dies bedeutet, dass die Anwendung immer vom Bereitstellungsort aus gestartet wird.  
  
- Automatische Aktualisierung, wenn neue Versionen freigegeben werden  
  
- Registrierung von Dateierweiterungen  
  
 Weitere Informationen zu ClickOnce finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a>Bereitstellen von WPF-Anwendungen  
 Die Bereitstellungs Optionen für eine WPF-Anwendung hängen von der Art der Anwendung ab. Aus Sicht der Bereitstellung verfügt WPF über drei bedeutende Anwendungs Typen:  
  
- Eigenständige Anwendungen  
  
- Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendungen  
  
- XAML-Browser Anwendungen (XBAPs).  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a>Bereitstellen von eigenständigen Anwendungen  
 Eigenständige Anwendungen werden entweder mithilfe von ClickOnce oder Windows Installer bereitgestellt. Bei beiden Methoden ist für die Ausführung der eigenständigen Anwendungen volle Vertrauenswürdigkeit erforderlich. Vollständige Vertrauenswürdigkeit wird automatisch eigenständigen Anwendungen gewährt, die mithilfe von Windows Installer bereitgestellt werden. Eigenständige Anwendungen, die mithilfe von ClickOnce bereitgestellt werden, werden nicht automatisch voll vertrauenswürdig eingestuft. Stattdessen zeigt ClickOnce ein Dialogfeld mit einer Sicherheitswarnung an, das Benutzer vor der Installation einer eigenständigen Anwendung akzeptieren müssen. Bei Annahme der Warnung wird die eigenständige Anwendung installiert und erhält volle Vertrauenswürdigkeit. Wird die Warnung abgelehnt, wird die eigenständige Anwendung nicht installiert.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a>Bereitstellen von Markup-XAML-Anwendungen  
 Nur-Markup- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten werden in der Regel auf Webservern veröffentlicht, wie z. b. HTML-Seiten und können mithilfe von Internet Explorer angezeigt werden. Markup-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Seiten werden mit einer teilweise vertrauenswürdigen Sandbox für die Sicherheit und Einschränkungen, die durch den Standardberechtigungssatz für die Internetzone definiert werden, ausgeführt. Dadurch wird eine entsprechende Sicherheits Sandbox für HTML-basierte Webanwendungen bereitgestellt.  
  
 Weitere Informationen zur Sicherheit für WPF-Anwendungen finden Sie unter [Sicherheit](../security-wpf.md).  
  
 Markup-only- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten können mithilfe von XCOPY oder Windows Installer im lokalen Dateisystem installiert werden. Diese Seiten können mithilfe von Internet Explorer oder Windows-Explorer angezeigt werden.  
  
 Weitere Informationen über XAML finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a>Bereitstellen von XAML-Browseranwendungen  
 XBAPs sind kompilierte Anwendungen, für die die Bereitstellung der folgenden drei Dateien erforderlich ist:  
  
- *Anwendungsname*.exe: die ausführbare Assemblyanwendungsdatei  
  
- *Anwendungsname*.xbap: das Bereitstellungsmanifest  
  
- *Anwendungsname*.exe.manifest: das Anwendungsmanifest  
  
> [!NOTE]
> Weitere Informationen zu Anwendungs- und Bereitstellungsmanifesten finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
 Diese Dateien werden erstellt, wenn eine XBAP erstellt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Browseranwendungsprojekts](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). XBAPs werden wie nur-Markup- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seiten in der Regel auf einem Webserver veröffentlicht und mithilfe von Internet Explorer angezeigt.  
  
 XBAPs können mithilfe einer beliebigen Bereitstellungs Verfahren für Clients bereitgestellt werden. ClickOnce wird jedoch empfohlen, da es die folgenden Funktionen bietet:  
  
1. Automatische Updates, wenn eine neue Version veröffentlicht wird  
  
2. Rechte für Rechte für die Ausführung der XBAP mit voller Vertrauenswürdigkeit.  
  
 Standardmäßig veröffentlicht ClickOnce Anwendungsdateien mit der Erweiterung „.deploy“. Dies kann problematisch sein, kann jedoch deaktiviert werden. Weitere Informationen finden Sie unter [Probleme mit der Server- und Clientkonfiguration in ClickOnce-Bereitstellungen](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Weitere Informationen zum Bereitstellen von XAML-Browser Anwendungen (XBAPs) finden Sie unter [Übersicht über WPF-XAML-Browser Anwendungen](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a>Installieren von .NET Framework  
 Zum Ausführen einer WPF-Anwendung muss das Microsoft .NET Framework auf dem Client installiert sein. Internet Explorer erkennt automatisch, ob-Clients mit .NET Framework installiert werden, wenn im Browser gehostete WPF-Anwendungen angezeigt werden. Wenn die .NET Framework nicht installiert ist, werden Benutzer von Internet Explorer aufgefordert, Sie zu installieren.  
  
 Um zu ermitteln, ob die .NET Framework installiert ist, enthält Internet Explorer eine Bootstrapperanwendung, die als Fall Back-Multipurpose Internet Mail Extensions (MIME)-Handler für Inhalts Dateien mit den folgenden Erweiterungen registriert ist:. XAML,. XPS,. XBAP und. Application. Wenn Sie zu diesen Dateitypen navigieren und die .NET Framework nicht auf dem Client installiert ist, fordert die Boots Trapper-Anwendung die Berechtigung zur Installation an. Wenn keine Berechtigung bereitgestellt wird, wird weder der .NET Framework noch die Anwendung installiert.  
  
 Wenn die Berechtigung erteilt wird, lädt Internet Explorer die .NET Framework mithilfe von Microsoft Bits (Bits) herunter und installiert sie. Nach der erfolgreichen Installation des .NET Framework wird die ursprünglich angeforderte Datei in einem neuen Browserfenster geöffnet.  
  
 Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework und Anwendungen](../../deployment/index.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)
- [Security](../security-wpf.md)
