---
title: "Sicherheit (WPF) | Microsoft Docs"
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
  - "Anwendungssicherheit [WPF]"
  - "Anwendungsweite Navigationssicherheit [WPF]"
  - "Funktionssteuerelemente [WPF], Sicherheit"
  - "Internet Explorer-Sicherheitseinstellungen [WPF]"
  - "Lose XAML-Dateien [WPF], Sandboxverhalten"
  - "Navigationssicherheit [WPF]"
  - "WebBrowser-Steuerelement [WPF], Sicherheit"
  - "WPF-Sicherheit"
  - "XAML-Dateien [WPF], Sandboxverhalten"
  - "XBAP-Sicherheit [WPF]"
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Sicherheit (WPF)
<a name="introduction"></a> Beim Entwickeln eigenständiger und im Browser gehosteter [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen müssen Sie das Sicherheitsmodell beachten. Eigenständige [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen werden mit uneingeschränkten Berechtigungen \([!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **FullTrust**\-Berechtigungssatz\) ausgeführt. Dabei ist es unerheblich, ob sie mit Windows Installer \(.msi\), Xcopy oder [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)] bereitgestellt wurden.  Die Bereitstellung teilweise vertrauenswürdiger, eigenständiger WPF\-Anwendungen mit ClickOnce wird nicht unterstützt.  Eine voll vertrauenswürdige Hostanwendung kann jedoch mithilfe des .NET Framework\-Add\-In\-Modells eine teilweise vertrauenswürdige <xref:System.AppDomain> erstellen.  Weitere Informationen finden Sie unter [Übersicht über WPF\-Add\-Ins](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen werden von [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] oder Firefox gehostet. Es handelt sich dabei entweder um [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)]\- oder um Loose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]\-Dokumente. Weitere Informationen finden Sie unter [Übersicht über WPF\-XAML\-Browseranwendungen](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen werden standardmäßig in einem teilweise vertrauenswürdigen Sicherheitsbereich \(Sandkasten\) ausgeführt, der auf den Standardberechtigungssatz für die [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **Internetzone** beschränkt ist.  Auf diese Weise werden im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen auf dieselbe Weise vom Clientcomputer isoliert wie typische Webanwendungen.  Eine XBAP kann abhängig von der Sicherheitszone der Bereitstellung\-URL und der Sicherheitskonfiguration des Clients Berechtigungen bis zur vollen Vertrauenswürdigkeit ausweiten.  Weitere Informationen finden Sie unter [WPF\-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
 In diesem Thema wird das Sicherheitsmodell für eigenständige und im Browser gehostete [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen erläutert.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Sichere Navigation](#SafeTopLevelNavigation)  
  
-   [Sicherheitseinstellungen für Webbrowsersoftware](#InternetExplorerSecuritySettings)  
  
-   [WebBrowser\-Steuerelement und Funktionssteuerelemente](#webbrowser_control_and_feature_controls)  
  
-   [Deaktivieren von APTCA\-Assemblys für teilweise vertrauenswürdige Clientanwendungen](#APTCA)  
  
-   [Sandkastenverhalten für Loose XAML\-Dateien](#LooseContentSandboxing)  
  
-   [Ressourcen zum Entwickeln von WPF\-Anwendungen, die die Sicherheit erhöhen](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## Sichere Navigation  
 Für [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] unterscheidet [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] zwei Navigationstypen: Anwendungsnavigation und Browsernavigation.  
  
 Als *Anwendungsnavigation* wird die Navigation zwischen Inhaltselementen in einer Anwendung bezeichnet, die in einem Browser gehostet wird.  Als *Browsernavigation* wird dagegen die Navigation bezeichnet, die die Inhalts\- und Speicherort\-URL des Browsers selbst ändert.  Die Beziehung zwischen Anwendungsnavigation \(in der Regel XAML\) und Browsernavigation \(in der Regel HTML\) wird in der folgenden Abbildung dargestellt:  
  
 ![Navigationsdiagramm](../../../docs/framework/wpf/media/safetoplevelnavigationfigure.png "SafeTopLevelNavigationFigure")  
  
 Der Inhaltstyp, der als sicheres Navigationsziel für eine [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] angesehen wird, wird hauptsächlich dadurch bestimmt, ob die Anwendungsnavigation oder die Browsernavigation verwendet wird.  
  
<a name="Application_Navigation_Security"></a>   
### Sicherheit der Anwendungsnavigation  
 Die Anwendungsnavigation wird als sicher betrachtet, wenn sie mit einem Paket\-[!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)] identifiziert werden kann, der vier Inhaltstypen unterstützt:  
  
|Inhaltstyp|Beschreibung|Beispiel für URI|  
|----------------|------------------|----------------------|  
|Ressource|Dateien, die einem Projekt mit einem **Resource**\-Buildtyp hinzugefügt werden.|`pack://application:,,,/MyResourceFile.xaml`|  
|Inhalt|Dateien, die einem Projekt mit einem **Content**\-Buildtyp hinzugefügt werden.|`pack://application:,,,/MyContentFile.xaml`|  
|Ursprungssite|Dateien, die einem Projekt mit einem **None**\-Buildtyp hinzugefügt werden.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Anwendungscode|XAML\-Ressourcen mit kompiliertem Code\-Behind.<br /><br /> \- oder \-<br /><br /> XAML\-Dateien, die einem Projekt mit einem **Page**\-Buildtyp hinzugefügt werden.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Weitere Informationen zu Anwendungsdatendateien und Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)] finden Sie unter [WPF\-Anwendungsressource, Inhalts\- und Datendateien](../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Zu Dateien dieser Inhaltstypen kann vom Benutzer oder programmgesteuert navigiert werden:  
  
-   **Benutzernavigation**.  Der Benutzer navigiert, indem er auf ein <xref:System.Windows.Documents.Hyperlink>\-Element klickt.  
  
-   **Programmgesteuerte Navigation**.  Die Anwendung navigiert, ohne den Benutzer einzubinden, z. B. durch Festlegen der <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>\-Eigenschaft.  
  
<a name="Browser_Navigation_Security"></a>   
### Sicherheit der Browsernavigation  
 Die Browsernavigation wird nur unter den folgenden Bedingungen als sicher betrachtet:  
  
-   **Benutzernavigation**.  Der Benutzer navigiert, indem er auf ein <xref:System.Windows.Documents.Hyperlink>\-Element klickt, das sich innerhalb des Haupt\-<xref:System.Windows.Navigation.NavigationWindow> befindet, nicht in einem geschachtelten <xref:System.Windows.Controls.Frame>.  
  
-   **Zone**.  Der Inhalt, durch den navigiert wird, befindet sich im Internet oder im lokalen Intranet.  
  
-   **Protokoll**.  Das Protokoll, das verwendet wird, ist entweder **http**, **https**, **file** oder **mailto**.  
  
 Wenn eine [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] versucht, auf eine Weise zu Inhalten zu navigieren, die nicht diesen Bedingungen entspricht, wird eine <xref:System.Security.SecurityException> ausgelöst.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## Sicherheitseinstellungen für Webbrowsersoftware  
 Die Sicherheitseinstellungen auf dem Computer bestimmen, welcher Zugriff jeder Webbrowsersoftware gewährt wird.  Webbrowsersoftware umfasst Anwendungen oder Komponenten, die [WinINet](http://go.microsoft.com/fwlink/?LinkId=179379)\- oder [UrlMon](http://go.microsoft.com/fwlink/?LinkId=179383)\-APIs verwenden, einschließlich Internet Explorer und PresentationHost.exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] stellt einen Mechanismus bereit, mit dem Sie die Funktionalität konfigurieren können, deren Ausführung durch oder von [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] zulässig ist. Dazu zählt Folgendes:  
  
-   Auf [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] basierende Komponenten  
  
-   ActiveX\-Steuerelemente und Plug\-Ins  
  
-   Downloads  
  
-   Skripterstellung  
  
-   Benutzerauthentifizierung  
  
 Die Auflistung der Funktionalitäten, die auf diese Weise gesichert werden können, wird auf Zonenbasis für die Zonen **Internet**, **Intranet**, **Vertrauenswürdige Sites** und **Eingeschränkte Sites** konfiguriert.  Die folgenden Schritte beschreiben, wie die Sicherheitseinstellungen konfiguriert werden:  
  
1.  Öffnen Sie die **Systemsteuerung**.  
  
2.  Klicken Sie auf **Netzwerk und Internet** und dann auf **Internetoptionen**.  
  
     Das Dialogfeld Internetoptionen wird angezeigt.  
  
3.  Wählen Sie auf der Registerkarte **Sicherheit** die Zone aus, für die die Sicherheitseinstellungen konfiguriert werden sollen.  
  
4.  Klicken Sie auf die Schaltfläche **Stufe anpassen**.  
  
     Das Dialogfeld **Sicherheitseinstellungen** wird geöffnet, in dem Sie die Sicherheitseinstellungen für die ausgewählte Zone konfigurieren können.  
  
     ![Dialogfeld Sicherheitseinstellungen](../../../docs/framework/wpf/media/wpfsecurityfigure1.PNG "WPFSecurityFigure1")  
  
> [!NOTE]
>  Sie können auch das Dialogfeld Internetoptionen von Internet Explorer verwenden.  Klicken Sie auf **Extras** und dann auf **Internetoptionen**.  
  
 Ab [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)] sind die folgenden Sicherheitseinstellungen speziell für [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] enthalten:  
  
-   **Loose XAML**.  Steuert, ob [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] zu Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Dateien navigieren kann.  \(Optionen Aktivieren, Deaktivieren und Eingabeaufforderung.\)  
  
-   **XAML\-Browseranwendungen**.  Steuert, ob [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] zu [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] navigieren und sie ausführen kann.  \(Optionen Aktivieren, Deaktivieren und Eingabeaufforderung.\)  
  
 Standardmäßig sind diese Einstellungen für die Zonen **Internet**, **Lokales Intranet** und **Vertrauenswürdige Sites** aktiviert und für die Zone **Eingeschränkte Sites** deaktiviert.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### Sicherheitsbezogene WPF\-Registrierungseinstellungen  
 Zusätzlich zu den Sicherheitseinstellungen über die Internetoptionen sind die folgenden Registrierungswerte für die selektive Blockierung sicherheitsrelevanter WPF\-Funktionen verfügbar.  Die Werte werden unter dem folgenden Schlüssel definiert:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 In der folgenden Tabelle sind die Werte aufgelistet, die festgelegt werden können.  
  
|Wertname|Werttyp|Wertdaten|  
|--------------|-------------|---------------|  
|XBAPDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
|LooseXamlDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
|WebBrowserDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
|MediaAudioDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
|MediaImageDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
|MediaVideoDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
|ScriptInteropDisallow|REG\_DWORD|1 \(nicht zulassen\); 0 \(zulassen\)|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## WebBrowser\-Steuerelement und Funktionssteuerelemente  
 Das <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement kann zum Hosten von Webinhalt verwendet werden.  Das <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement umschließt das zugrunde liegende WebBrowser\-ActiveX\-Steuerelement.  WPF bietet eine gewisse Unterstützung zum Sichern der Anwendung, wenn Sie mit dem <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement nicht vertrauenswürdigen Webinhalt hosten.  Einige Sicherheitsfunktionen müssen jedoch mit dem <xref:System.Windows.Controls.WebBrowser>\-Steuerelement direkt durch die Anwendungen angewendet werden.  Weitere Informationen zum WebBrowser\-ActiveX\-Steuerelement finden Sie unter [WebBrowser Control Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
>  Dieser Abschnitt gilt auch für das <xref:System.Windows.Controls.Frame>\-Steuerelement, da es mithilfe des <xref:System.Windows.Controls.WebBrowser> zu HTML\-Inhalt navigiert.  
  
 Wenn das <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement zum Hosten von nicht vertrauenswürdigem Webinhalt verwendet wird, sollte die Anwendung eine teilweise vertrauenswürdige <xref:System.AppDomain> verwenden, um den Anwendungscode von potenziell bösartigem HTML\-Skriptcode zu isolieren.  Dies gilt besonders, wenn die Anwendung mit dem gehosteten Skript mit der <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A>\-Methode und der <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>\-Eigenschaft interagiert.  Weitere Informationen finden Sie unter [Übersicht über WPF\-Add\-Ins](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Wenn die Anwendung das <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement verwendet, ist das Aktivieren der Internet Explorer\-Funktionssteuerelemente eine weitere Möglichkeit, um die Sicherheit zu erhöhen und Angriffe zu verhindern.  Funktionssteuerelemente sind Ergänzungen zu Internet Explorer, mit denen Administratoren und Entwickler Funktionen von Internet Explorer und Anwendungen konfigurieren können, die das vom <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement umschlossene WebBrowser\-ActiveX\-Steuerelement hosten.  Funktionssteuerelemente können mithilfe der [CoInternetSetFeatureEnabled](http://go.microsoft.com/fwlink/?LinkId=179394)\-Funktion oder durch das Ändern von Werten in der Registrierung konfiguriert werden.  Weitere Informationen zu Funktionssteuerelementen finden Sie unter [Introduction to Feature Controls](http://go.microsoft.com/fwlink/?LinkId=179390) und [Internet Feature Controls](http://go.microsoft.com/fwlink/?LinkId=179392).  
  
 Wenn Sie eine eigenständige WPF\-Anwendung entwickeln, die das <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement verwendet, aktiviert WPF automatisch die folgenden Funktionssteuerelemente für die Anwendung.  
  
|Funktionssteuerelement|  
|----------------------------|  
|FEATURE\_MIME\_HANDLING|  
|FEATURE\_MIME\_SNIFFING|  
|FEATURE\_OBJECT\_CACHING|  
|FEATURE\_SAFE\_BINDTOOBJECT|  
|FEATURE\_WINDOW\_RESTRICTIONS|  
|FEATURE\_ZONE\_ELEVATION|  
|FEATURE\_RESTRICT\_FILEDOWNLOAD|  
|FEATURE\_RESTRICT\_ACTIVEXINSTALL|  
|FEATURE\_ADDON\_MANAGEMENT|  
|FEATURE\_HTTP\_USERNAME\_PASSWORD\_DISABLE|  
|FEATURE\_SECURITYBAND|  
|FEATURE\_UNC\_SAVEDFILECHECK|  
|FEATURE\_VALIDATE\_NAVIGATE\_URL|  
|FEATURE\_DISABLE\_TELNET\_PROTOCOL|  
|FEATURE\_WEBOC\_POPUPMANAGEMENT|  
|FEATURE\_DISABLE\_LEGACY\_COMPRESSION|  
|FEATURE\_SSLUX|  
  
 Da diese Funktionssteuerelemente ohne Bedingung aktiviert werden, können sie möglicherweise voll vertrauenswürdige Anwendungen beeinträchtigen.  In diesem Fall kann das entsprechende Funktionssteuerelement deaktiviert werden, wenn kein Sicherheitsrisiko für die jeweilige Anwendung und den gehosteten Inhalt besteht.  
  
 Funktionssteuerelemente werden von dem Prozess angewendet, der das WebBrowser\-ActiveX\-Objekt instanziiert.  Daher wird dringend empfohlen, beim Erstellen einer eigenständigen Anwendung, die zu nicht vertrauenswürdigem Inhalt navigieren kann, zusätzliche Funktionssteuerelemente zu aktivieren.  
  
> [!NOTE]
>  Diese Empfehlung basiert auf allgemeinen Empfehlungen für MSHTML\- und SHDOCVW\-Hostsicherheit.  Weitere Informationen finden Sie unter [The MSHTML Host Security FAQ: Part I of II](http://go.microsoft.com/fwlink/?LinkId=179396) und [The MSHTML Host Security FAQ: Part II of II](http://go.microsoft.com/fwlink/?LinkId=179415).  
  
 Es wird empfohlen, für die ausführbare Datei die folgenden Funktionssteuerelemente durch Festlegen des Registrierungswerts auf 1 zu aktivieren.  
  
|Funktionssteuerelement|  
|----------------------------|  
|FEATURE\_ACTIVEX\_REPURPOSEDETECTION|  
|FEATURE\_BLOCK\_LMZ\_IMG|  
|FEATURE\_BLOCK\_LMZ\_OBJECT|  
|FEATURE\_BLOCK\_LMZ\_SCRIPT|  
|FEATURE\_RESTRICT\_RES\_TO\_LMZ|  
|FEATURE\_RESTRICT\_ABOUT\_PROTOCOL\_IE7|  
|FEATURE\_SHOW\_APP\_PROTOCOL\_WARN\_DIALOG|  
|FEATURE\_LOCALMACHINE\_LOCKDOWN|  
|FEATURE\_FORCE\_ADDR\_AND\_STATUS|  
|FEATURE\_RESTRICTED\_ZONE\_WHEN\_FILE\_NOT\_FOUND|  
  
 Es wird empfohlen, für die ausführbare Datei das folgende Funktionssteuerelement durch Festlegen des Registrierungswerts auf 0 zu deaktivieren.  
  
|Funktionssteuerelement|  
|----------------------------|  
|FEATURE\_ENABLE\_SCRIPT\_PASTE\_URLACTION\_IF\_PROMPT|  
  
 Wenn Sie eine teilweise vertrauenswürdige [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] ausführen, die ein <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement in [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] enthält, hostet WPF das WebBrowser\-ActiveX\-Steuerelement im Adressbereich des Internet Explorer\-Prozesses.  Da das WebBrowser\-ActiveX\-Steuerelement im [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)]\-Prozess gehostet wird, sind alle Funktionssteuerelemente für Internet Explorer auch für das WebBrowser\-ActiveX\-Steuerelement aktiviert.  
  
 In Internet Explorer ausgeführte XBAPs erhalten im Vergleich zu normalen eigenständigen Anwendungen ebenfalls eine zusätzliche Sicherheitsebene.  Diese zusätzliche Sicherheit ergibt sich daraus, dass Internet Explorer und daher das WebBrowser\-ActiveX\-Steuerelement unter [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] und [!INCLUDE[win7](../../../includes/win7-md.md)] standardmäßig im geschützten Modus ausgeführt werden.  Weitere Informationen zum geschützten Modus finden Sie unter [Understanding and Working in Protected Mode Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
>  Wenn Sie versuchen, in der Internetzone eine XBAP auszuführen, die ein <xref:System.Windows.Controls.WebBrowser>\-WPF\-Steuerelement in Firefox enthält, wird eine <xref:System.Security.SecurityException> ausgelöst.  Dies geschieht aufgrund der WPF\-Sicherheitsrichtlinie.  
  
<a name="APTCA"></a>   
## Deaktivieren von APTCA\-Assemblys für teilweise vertrauenswürdige Clientanwendungen  
 Wenn verwaltete Assemblys in GAC \([!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)]\) installiert werden, werden sie voll vertrauenswürdig, weil der Benutzer für die Installation eine explizite Berechtigung bereitstellen muss.  Da sie voll vertrauenswürdig sind, können sie nur von voll vertrauenswürdigen verwalteten Clientanwendungen verwendet werden.  Damit teilweise vertrauenswürdige Anwendungen sie verwenden können, müssen sie mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(APTCA\) markiert werden.  Nur Assemblys, die sich in einem Test bei der Ausführung in teilweiser Vertrauenswürdigkeit als sicher erwiesen haben, sollten mit diesem Attribut markiert werden.  
  
 Eine APTCA\-Assembly kann jedoch nach der Installation in GAC \([!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)]\) einen Sicherheitsmangel aufweisen.  Nachdem ein Sicherheitsmangel entdeckt wurde, können Assemblyherausgeber ein Sicherheitsupdate erzeugen, um das Problem in vorhandenen Installationen zu beheben und Installationen zu schützen, die nach der Entdeckung des Problems erfolgen.  Das Update kann die Assembly deinstallieren, was jedoch zur Unterbrechung anderer voll vertrauenswürdiger Clientanwendungen führen kann, die diese Assembly verwenden.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] stellt einen Mechanismus bereit, mit dem eine APTCA\-Assembly für teilweise vertrauenswürdige [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] deaktiviert werden kann, ohne die APTCA\-Assembly zu deinstallieren.  
  
 Zum Deaktivieren einer APTCA\-Assembly müssen Sie einen speziellen Registrierungsschlüssel erstellen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Im Folgenden wird ein Beispiel angezeigt:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Dieser Schlüssel erstellt einen Eintrag für die APTCA\-Assembly.  Sie müssen außerdem einen Wert in diesem Schlüssel erstellen, der die Assembly aktiviert oder deaktiviert.  Im Folgenden sind die Details für den Wert aufgeführt:  
  
-   Wertname: **APTCA\_FLAG**  
  
-   Werttyp: **REG\_DWORD**  
  
-   Wertdaten: **1** \(deaktivieren\); **0** \(aktivieren\)  
  
 Muss eine Assembly für teilweise vertrauenswürdige Clientanwendungen deaktiviert werden, können Sie ein Update zum Erstellen des Registrierungsschlüssels und des Werts schreiben.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)]\-Kernassemblys sind von dieser Art der Deaktivierung nicht betroffen, da sie für die Ausführung von verwalteten Anwendungen erforderlich sind.  Die Unterstützung zur Deaktivierung von APTCA\-Assemblys wird hauptsächlich für Anwendungen von Drittanbietern bereitgestellt.  
  
<a name="LooseContentSandboxing"></a>   
## Sandkastenverhalten für Loose XAML\-Dateien  
 Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Dateien sind Markup\-XAML\-Dateien, die nicht von CodeBehind\-, Ereignishandler\- oder anwendungsspezifischen Assemblys abhängen.  Wenn zu Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Dateien direkt vom Browser navigiert wird, werden sie basierend auf dem Standardberechtigungssatz für die Internetzone in einem Sicherheitssandkasten geladen.  
  
 Das Sicherheitsverhalten ändert sich jedoch, wenn in einer eigenständigen Anwendung entweder von einem <xref:System.Windows.Navigation.NavigationWindow> oder einem <xref:System.Windows.Controls.Frame> zu Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Dateien navigiert wird.  
  
 In beiden Fällen erbt die Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Datei, zu der navigiert wird, die Berechtigung ihrer Hostanwendung.  Dieses Verhalten kann jedoch aus Sicherheitsgründen auch unerwünscht sein, besonders wenn eine Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Datei von einer Entität erzeugt wurde, die entweder nicht vertrauenswürdig oder unbekannt ist.  Dieser Inhaltstyp wird als *externer Inhalt* bezeichnet. Sowohl <xref:System.Windows.Controls.Frame> als auch <xref:System.Windows.Navigation.NavigationWindow> kann so konfiguriert werden, dass der Inhalt, zu dem navigiert wird, isoliert wird.  Die Isolation wird durch Festlegen der **SandboxExternalContent**\-Eigenschaft auf true erzielt, wie in den folgenden Beispielen für <xref:System.Windows.Controls.Frame> und <xref:System.Windows.Navigation.NavigationWindow> gezeigt:  
  
 [!code-xml[SecurityOverviewSnippets#FrameMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xml[SecurityOverviewSnippets#NavigationWindowMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Mit dieser Einstellung wird der externe Inhalt in einen anderen Prozess als den Prozess geladen, der die Anwendung hostet.  Dieser Prozess ist auf den Standardberechtigungssatz für die Internetzone beschränkt und isoliert ihn effizient von der Hostanwendung und dem Clientcomputer.  
  
> [!NOTE]
>  Obwohl die Navigation zu Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\-Dateien von einem <xref:System.Windows.Navigation.NavigationWindow> oder <xref:System.Windows.Controls.Frame> in einer eigenständigen Anwendung auf Grundlage der WPF\-Browserhostinginfrastruktur implementiert wird und den PresentationHost\-Prozess beinhaltet, ist die Sicherheitsebene etwas niedriger, als wenn der Inhalt unter [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] und [!INCLUDE[win7](../../../includes/win7-md.md)] direkt in Internet Explorer geladen wird \(ebenfalls über PresentationHost\). Dies liegt daran, dass eine eigenständige WPF\-Anwendung, die einen Webbrowser verwendet, die zusätzliche Sicherheitsfunktion für den geschützten Modus von Internet Explorer nicht bereitstellt.  
  
<a name="BestPractices"></a>   
## Ressourcen zum Entwickeln von WPF\-Anwendungen, die die Sicherheit erhöhen  
 Nachfolgend sind einige zusätzliche Ressourcen zum Entwickeln von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen aufgeführt, die die Sicherheit erhöhen:  
  
|Bereich|Ressource|  
|-------------|---------------|  
|Verwalteter Code|[Patterns and Practices\-Sicherheitsleitfaden für Anwendungen](http://go.microsoft.com/fwlink/?LinkId=117426) \(möglicherweise in englischer Sprache\)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[Codezugriffssicherheit](../../../docs/framework/misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[ClickOnce\-Sicherheit und Bereitstellung](../Topic/ClickOnce%20Security%20and%20Deployment.md)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[WPF\-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../docs/framework/wpf/wpf-partial-trust-security.md)|  
  
## Siehe auch  
 [WPF\-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../docs/framework/wpf/wpf-partial-trust-security.md)   
 [WPF\-Sicherheitsstrategie – Plattformsicherheit](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [WPF\-Sicherheitsstrategie – Sicherheitsentwicklung](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)   
 [Patterns and Practices\-Sicherheitsleitfaden für Anwendungen](http://go.microsoft.com/fwlink/?LinkId=117426)   
 [Codezugriffssicherheit](../../../docs/framework/misc/code-access-security.md)   
 [ClickOnce\-Sicherheit und Bereitstellung](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Übersicht über XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)