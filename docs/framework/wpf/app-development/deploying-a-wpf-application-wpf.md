---
title: "Bereitstellen von WPF-Anwendungen (WPF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bereitstellung [WPF], Anwendungen"
  - "WPF-Anwendungen, Bereitstellung"
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Bereitstellen von WPF-Anwendungen (WPF)
Nach dem Erstellen müssen [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen bereitgestellt werden.  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] bieten verschiedene Bereitstellungstechnologien.  Die für die Bereitstellung einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung eingesetzte Technologie ist abhängig vom Anwendungstyp.  Dieses Thema bietet eine kurze Übersicht über die einzelnen Bereitstellungstechnologien. Außerdem erfahren Sie, wie diese Bereitstellungstechnologien im Zusammenhang mit den Bereitstellungsvoraussetzungen für die verschiedenen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungstypen verwendet werden.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Deployment_Technologies"></a>   
## Bereitstellungstechnologien  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] schließen mehrere Bereitstellungstechnologien ein, u. a.:  
  
-   Bereitstellung mit XCopy  
  
-   Bereitstellung mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]  
  
-   Bereitstellung mit [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]  
  
<a name="XCopy_Deployment"></a>   
### Bereitstellung mit XCopy  
 Bereitstellung mit XCopy bedeutet, dass mithilfe des XCopy\-Befehlszeilenprogramms Dateien von einem Speicherort an einen anderen kopiert werden.  Diese Art der Bereitstellung ist in den folgenden Fällen geeignet:  
  
-   Es handelt sich um eine unabhängige, in sich geschlossene Anwendung.  Der Client muss für die Ausführung nicht aktualisiert werden.  
  
-   Anwendungsdateien müssen zwischen Speicherorten verschoben werden, zum Beispiel vom Ort der Erstellung \(lokaler Datenträger, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)]\-Dateifreigabe usw.\) an den Ort der Veröffentlichung \(Website, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)]\-Dateifreigabe usw.\).  
  
-   Die Anwendung erfordert keine Shell\-Integration \(Verknüpfung im Startmenü, Symbol auf dem Desktop usw.\).  
  
 XCopy eignet sich zwar für einfache Bereitstellungsszenarien, bietet jedoch zu wenige Funktionen für komplexe Bereitstellungen.  Insbesondere fällt bei der Verwendung von XCopy häufig ein Mehraufwand für die Erstellung, Ausführung und Pflege von Skripten für die solide Verwaltung der Bereitstellung an.  Außerdem werden bei XCopy Versionsverwaltung, Deinstallation und Rollback nicht unterstützt.  
  
<a name="Windows_Installer"></a>   
### Windows Installer  
 Mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] können Anwendungen als eigenständige ausführbare Dateien gepackt werden, die auf einfache Weise an Clients verteilt und ausgeführt werden können.  Darüber hinaus wird [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] mit [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] installiert und ermöglicht die Einbindung in Desktop, Startmenü und das Fenster für installierte Software in der Systemsteuerung.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] vereinfacht die Installation und Deinstallation von Anwendungen. Es bietet jedoch keine Versionsverwaltung, das heißt, die Möglichkeit sicherzustellen, dass die installierten Anwendungen immer auf dem neuesten Stand sind.  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] finden Sie unter [Windows Installer Deployment](http://msdn.microsoft.com/de-de/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
<a name="ClickOnce_Deployment"></a>   
### ClickOnce\-Bereitstellung  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] ermöglicht die Bereitstellung von Nicht\-Webanwendungen im Webformat. Anwendungen werden auf Web\- oder Dateiservern veröffentlicht und von dort bereitgestellt.  [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] unterstützt zwar nicht alle Clientfeatures, die von den mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] installierten Anwendungen bereitgestellt werden, es steht jedoch eine Teilmenge dieser Features zur Verfügung. Hierzu gehören die folgenden Funktionen:  
  
-   Einbindung in Startmenü und das Fenster für installierte Software in der Systemsteuerung  
  
-   Versionsverwaltung, Rollback und Deinstallation  
  
-   Online\-Installationsmodus; dies bedeutet, dass die Anwendung immer vom Bereitstellungsort aus gestartet wird.  
  
-   Automatische Aktualisierung, wenn neue Versionen freigegeben werden  
  
-   Registrierung von Dateierweiterungen  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] finden Sie unter [ClickOnce\-Sicherheit und Bereitstellung](../Topic/ClickOnce%20Security%20and%20Deployment.md).  
  
<a name="Deploying_WPF_Applications"></a>   
## Bereitstellen von WPF\-Anwendungen  
 Die Bereitstellungsoptionen für eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung sind abhängig vom Typ der Anwendung.  Im Rahmen der Bereitstellung gibt es bei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] drei Hauptanwendungstypen:  
  
-   Eigenständige Anwendungen  
  
-   Markup\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Anwendungen  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### Bereitstellen von eigenständigen Anwendungen  
 Eigenständige Anwendungen werden mit [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] oder mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] bereitgestellt.  Bei beiden Methoden ist für die Ausführung der eigenständigen Anwendungen volle Vertrauenswürdigkeit erforderlich.  Eigenständigen Anwendungen, die mit [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] bereitgestellt werden, wird die volle Vertrauenswürdigkeit automatisch gewährt.  Bei der Bereitstellung mit [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] wird die volle Vertrauenswürdigkeit jedoch nicht automatisch gewährt.  [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] zeigt stattdessen eine Sicherheitswarnung an, die akzeptiert werden muss, bevor eine eigenständige Anwendung installiert wird.  Bei Annahme der Warnung wird die eigenständige Anwendung installiert und erhält volle Vertrauenswürdigkeit.  Wird die Warnung abgelehnt, wird die eigenständige Anwendung nicht installiert.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### Bereitstellen von Markup\-XAML\-Anwendungen  
 Markup\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten werden normalerweise wie [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]\-Seiten auf Webservern veröffentlicht und können mit [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] angezeigt werden.  Markup\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten werden mit einer teilweise vertrauenswürdigen Sandbox für die Sicherheit und Einschränkungen, die durch den Standardberechtigungssatz für die Internetzone definiert werden, ausgeführt.  Dies stellt eine Sandbox für die Sicherheit bereit, die der von [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]\-basierten Webanwendungen entspricht.  
  
 Weitere Informationen zur Sicherheit von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen finden Sie unter [Sicherheit](../../../../docs/framework/wpf/security-wpf.md).  
  
 Markup\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten können mit XCopy oder [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] im lokalen Dateisystem installiert werden.  Diese Seiten können mit [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] oder [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]\-Explorer angezeigt werden.  
  
 Weitere Informationen über XAML finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### Bereitstellen von XAML\-Browseranwendungen  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sind kompilierte Anwendungen, bei denen die folgenden drei Dateien für die Bereitstellung erforderlich sind:  
  
-   *Anwendungsname*.exe: die ausführbare Assemblyanwendungsdatei  
  
-   *Anwendungsname*.xbap: das Bereitstellungsmanifest  
  
-   *Anwendungsname*.exe.manifest: das Anwendungsmanifest  
  
> [!NOTE]
>  Weitere Informationen zu Anwendungs\- und Bereitstellungsmanifesten finden Sie unter [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 Diese Dateien werden erzeugt, wenn eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] erstellt wird.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines neuen WPF\-Browseranwendungsprojekts](http://msdn.microsoft.com/de-de/72ef4d90-e163-42a1-8df0-ea7ccfd1901f).  Wie Markup\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten werden [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] normalerweise auf einem Webserver veröffentlicht und mit [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] angezeigt.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] können mit einer beliebigen Bereitstellungstechnik auf Clients bereitgestellt werden.  [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] wird jedoch empfohlen, da es die folgenden Funktionen bietet:  
  
1.  Automatische Updates, wenn eine neue Version veröffentlicht wird  
  
2.  Berechtigungserweiterungen für die als voll vertrauenswürdig ausgeführte [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]  
  
 Standardmäßig veröffentlicht ClickOnce Anwendungsdateien mit der Erweiterung .deploy.  Dies kann problematisch sein, kann jedoch deaktiviert werden.  Weitere Informationen finden Sie unter [Probleme mit der Server\- und Clientkonfiguration in ClickOnce\-Bereitstellungen](../Topic/Server%20and%20Client%20Configuration%20Issues%20in%20ClickOnce%20Deployments.md).  
  
 Weitere Informationen zur Bereitstellung von [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] finden Sie unter [Übersicht über WPF\-XAML\-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## Installieren von .NET Framework  
 Damit eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung ausgeführt werden kann, muss [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] auf dem Client installiert sein.  [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] erkennt automatisch, ob auf den Clients [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installiert ist, wenn im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen angezeigt werden.  Falls [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] nicht installiert ist, zeigt [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] eine Installationsaufforderung an.  
  
 Um ermitteln zu können, ob [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installiert ist, enthält [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] eine Bootstrapper\-Anwendung, die als Fallback\-[!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)]\-Handler für Inhaltsdateien mit den Erweiterungen .xaml, .xps, .xbap und .application registriert wird.  Wenn Sie zu diesen Dateiformaten navigieren, ohne dass [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] auf dem Client installiert ist, fordert die Bootstrapper\-Anwendung die Erlaubnis zur Installation an.  Wird dieser Anforderung nicht stattgegeben, wird weder [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] noch die Anwendung installiert.  
  
 Wird die Erlaubnis gewährt, wird [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] von [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] mithilfe von [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)] heruntergeladen und installiert.  Nach der Installation von [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] wird die ursprünglich angeforderte Datei in einem neuen Browserfenster geöffnet.  
  
 Die automatische Erkennung von [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] steht auf [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)]\-, [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)]\- und [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)]\-Clients mit [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] oder höher zur Verfügung.  
  
 Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework und Anwendungen](../../../../docs/framework/deployment/net-framework-and-applications.md).  
  
## Siehe auch  
 [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)