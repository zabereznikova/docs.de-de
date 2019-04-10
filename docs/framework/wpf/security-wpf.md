---
title: Sicherheit (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: 968913a52a1d86746498aed7c97b63594d346a31
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313566"
---
# <a name="security-wpf"></a>Sicherheit (WPF)
<a name="introduction"></a> Wenn Sie Windows Presentation Foundation (WPF)-eigenständige und im Browser gehostete Anwendungen zu entwickeln, müssen Sie das Sicherheitsmodell berücksichtigen. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] eigenständige Anwendungen werden mit uneingeschränkten Berechtigungen ausgeführt ( [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **FullTrust** Berechtigungssatz), ob mithilfe von Windows Installer (MSI), XCopy, bereitgestellt oder [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]. Die Bereitstellung teilweise vertrauenswürdiger eigenständiger WPF-Anwendungen mit ClickOnce wird nicht unterstützt. Eine voll vertrauenswürdige hostanwendung kann jedoch eine teilweise vertrauenswürdige erstellen <xref:System.AppDomain> mit dem .NET Framework-Add-in-Modell. Weitere Informationen finden Sie unter [Übersicht über WPF-Add-Ins](./app-development/wpf-add-ins-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Browser-gehostete Anwendungen gehostet werden, indem [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] oder Firefox und kann entweder [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] oder loose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] Dokumenten Weitere Informationen finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Führen Sie im Browser gehostete Anwendungen in einer teilweise vertrauenswürdigen Sicherheits-Sandbox, standardmäßig die beschränkt der Standardwert ist [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **Internet** zone Berechtigungssatz. Dies effektiv isoliert [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] im Browser gehostete Anwendungen auf dem Clientcomputer auf die gleiche Weise, dass Sie isoliert werden typische Webanwendungen erwarten. Eine XBAP kann, abhängig von der Sicherheitszone der Bereitstellungs-URL und der Sicherheitskonfiguration des Clients, Berechtigungen bis zur vollen Vertrauenswürdigkeit erhöhen. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md).  
  
 Dieses Thema beschreibt das Sicherheitsmodell für Windows Presentation Foundation (WPF)-eigenständige und im Browser gehostete Anwendungen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Sichere Navigation](#SafeTopLevelNavigation)  
  
-   [Sicherheitseinstellungen für webbrowsende Software](#InternetExplorerSecuritySettings)  
  
-   [WebBrowser-Steuerelement und Funktionssteuerelemente](#webbrowser_control_and_feature_controls)  
  
-   [Deaktivieren von APTCA-Assemblys für teilweise vertrauenswürdige Clientanwendungen](#APTCA)  
  
-   [Sandkastenverhalten für Loose XAML-Dateien](#LooseContentSandboxing)  
  
-   [Ressourcen zum Entwickeln von WPF-Anwendungen, die die Sicherheit erhöhen](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## <a name="safe-navigation"></a>Sichere Navigation  
 Für [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Navigation zwei Navigationstypen: Anwendungsnavigation und Browsernavigation.  
  
 Als *Anwendungsnavigation* wird die Navigation zwischen Inhaltselementen in einer Anwendung bezeichnet, die in einem Browser gehostet wird. Als *Browsernavigation* wird die Navigation bezeichnet, die die Inhalts- und Speicherort-URL eines Browsers selbst ändert. Die Beziehung zwischen Anwendungsnavigation (in der Regel XAML) und Browsernavigation (in der Regel HTML) wird in der folgenden Abbildung dargestellt:
  
 ![Beziehung zwischen Anwendungsnavigation und Browsernavigation.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Der Typ des Inhalts, der für sicher gilt eine [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] , zu dem navigiert werden hauptsächlich dadurch bestimmt, ob Anwendungsnavigation oder Browsernavigation verwendet wird.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Sicherheit von Anwendungsnavigation  
 Anwendungsnavigation wird als sicher betrachtet, wenn sie mit einem Paket-identifiziert werden kann [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)], die vier Inhaltstypen unterstützt:  
  
|Inhaltstyp|Beschreibung|URI-Beispiel|  
|------------------|-----------------|-----------------|  
|Ressource|Dateien, die einem Projekt mit einem Buildtyp hinzugefügt werden **Ressource**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|Dateien, die einem Projekt mit einem Buildtyp hinzugefügt werden **Content**.|`pack://application:,,,/MyContentFile.xaml`|  
|Ursprungswebsite|Dateien, die einem Projekt mit einem Buildtyp hinzugefügt werden **keine**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Anwendungscode|XAML-Ressourcen mit kompiliertem Code-Behind<br /><br /> - oder - <br /><br /> XAML-Dateien, die einem Projekt mit einem Buildtyp hinzugefügt werden **Seite**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Weitere Informationen zu Anwendungsdatendateien und Pack [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)], finden Sie unter [WPF-Anwendungsressource, Inhalt und Datendateien](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 Ein Navigieren zu Dateien dieser Inhaltstypen kann sowohl durch einen Benutzer als auch programmgesteuert erfolgen:  
  
-   **Benutzernavigation**. Der Benutzer navigiert, indem Sie auf eine <xref:System.Windows.Documents.Hyperlink> Element.  
  
-   **Programmgesteuerte Navigation** Die Anwendung navigiert, ohne den Benutzer, z. B. durch Festlegen der <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> Eigenschaft.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Sicherheit von Browsernavigation  
 Browsernavigation wird nur unter den folgenden Bedingungen als sicher betrachtet:  
  
-   **Benutzernavigation**. Der Benutzer navigiert, indem Sie auf eine <xref:System.Windows.Documents.Hyperlink> -Element, das innerhalb des Haupt- <xref:System.Windows.Navigation.NavigationWindow>, nicht in einer geschachtelten <xref:System.Windows.Controls.Frame>.  
  
-   **Zone**. Der Inhalt, in dem navigiert wird, befindet sich im Internet oder im lokalen Intranet.  
  
-   **Protokoll**. Das verwendete Protokoll ist entweder **http**, **Https**, **Datei**, oder **Mailto**.  
  
 Wenn ein [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] versucht, Inhalte in einer Weise zu navigieren, die diesen Bedingungen nicht erfüllt eine <xref:System.Security.SecurityException> ausgelöst.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Sicherheitseinstellungen für webbrowsende Software  
 Die Sicherheitseinstellungen auf dem Computer bestimmen, welcher Zugriff jeder webbrowsenden Software gewährt wird. Software gehören alle Anwendungen oder Komponenten, die verwendet die [WinINet](https://go.microsoft.com/fwlink/?LinkId=179379) oder [UrlMon](https://go.microsoft.com/fwlink/?LinkId=179383) APIs, einschließlich Internet Explorer und PresentationHost.exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] Stellt einen Mechanismus, mit dem können Sie konfigurieren die Funktionen, die durch oder aus ausgeführt werden darf [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], einschließlich der folgenden:  
  
-   .NET Framework basierende Komponenten  
  
-   ActiveX-Steuerelemente und Plug-Ins  
  
-   Downloads  
  
-   Skripterstellung  
  
-   Benutzerauthentifizierung  
  
 Die Auflistung der Funktionen, die auf diese Weise gesichert werden kann erfolgt auf Grundlage einzelner Zonen für die **Internet**, **Intranet**, **vertrauenswürdige Sites**, und  **Eingeschränkte Sites** Zonen. Die folgenden Schritte beschreiben, wie die Sicherheitseinstellungen konfiguriert werden:  
  
1. Open **Systemsteuerung**.  
  
2. Klicken Sie auf **Netzwerk und Internet** , und klicken Sie dann auf **Internetoptionen**.  
  
     Das Dialogfeld "Internetoptionen" wird angezeigt.  
  
3. Auf der **Sicherheit** Registerkarte, wählen Sie die Zone so konfigurieren Sie die Sicherheitseinstellungen für.  
  
4. Klicken Sie auf die **Stufe** Schaltfläche.  
  
     Die **Sicherheitseinstellungen** Dialogfeld wird angezeigt, und Sie können die Sicherheitseinstellungen für die ausgewählte Zone konfigurieren.  
  
     ![Screenshot, das Dialogfeld Sicherheitseinstellungen zeigt.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
>  Sie können auch aus Internet Explorer zum Dialogfeld „Internetoptionen“ gelangen. Klicken Sie auf **Tools** , und klicken Sie dann auf **Internetoptionen**.  
  
 Beginnend mit [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)], die folgenden Sicherheitseinstellungen speziell für .NET Framework sind enthalten:  
  
-   **Loose XAML**. Steuerelemente, ob [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] können zu navigieren und loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien. (Optionen „Aktivieren“, „Deaktivieren“ und „Bestätigen“.)  
  
-   **XAML-Browseranwendungen**. Steuerelemente, ob [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] können zu navigieren, und führen Sie [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]. (Optionen „Aktivieren“, „Deaktivieren“ und „Bestätigen“.)  
  
 Standardmäßig diese Einstellungen sind alle aktiviert für die **Internet**, **lokales Intranet**, und **vertrauenswürdige Sites** Zonen und deaktiviert Sie für die **eingeschränkte Sites**  Zone.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### <a name="security-related-wpf-registry-settings"></a>Sicherheitsbezogene WPF-Registrierungseinstellungen  
 Zusätzlich zu den Sicherheitseinstellungen, die über die Internetoptionen verfügbar sind, sind die folgenden Registrierungswerte für die selektive Blockierung einiger sicherheitsrelevanter WPF-Funktionen verfügbar. Die Werte werden unter dem folgenden Schlüssel definiert:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 In der folgenden Tabelle sind die Werte aufgelistet, die festgelegt werden können.  
  
|Wertname|Werttyp|Wertdaten|  
|----------------|----------------|----------------|  
|XBAPDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
|LooseXamlDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
|WebBrowserDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
|MediaAudioDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
|MediaImageDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
|MediaVideoDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
|ScriptInteropDisallow|REG_DWORD|1 = nicht zulassen; 0 = zulassen|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## <a name="webbrowser-control-and-feature-controls"></a>WebBrowser-Steuerelement und Funktionssteuerelemente  
 Die WPF <xref:System.Windows.Controls.WebBrowser> Steuerelement zum Hosten von Webinhalt verwendet werden kann. Die WPF <xref:System.Windows.Controls.WebBrowser> Steuerelement umschließt das zugrunde liegende WebBrowser ActiveX-Steuerelement. WPF bietet eine gewisse Unterstützung zum Schützen der Anwendung, bei der Verwendung von WPF <xref:System.Windows.Controls.WebBrowser> zu hostende Steuerelement als Web-Inhalte nicht vertrauenswürdig eingestuft. Allerdings müssen einige Sicherheitsfunktionen angewendet werden, direkt von den Anwendungen, die mit der <xref:System.Windows.Controls.WebBrowser> Steuerelement. Weitere Informationen über das WebBrowser ActiveX-Steuerelement finden Sie unter [WebBrowser Control Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
>  Dieser Abschnitt gilt auch für die <xref:System.Windows.Controls.Frame> steuern, da er verwendet den <xref:System.Windows.Controls.WebBrowser> zu HTML-Inhalt navigiert.  
  
 Wenn das WPF <xref:System.Windows.Controls.WebBrowser> Steuerelement wird zum Hosten von nicht vertrauenswürdigem Webinhalt verwendet, die Anwendung sollte eine teilweise vertrauenswürdige verwenden <xref:System.AppDomain> können Sie den Anwendungscode von potenziell bösartigem HTML-Skriptcode zu isolieren. Dies ist insbesondere dann, wenn Ihre Anwendung mit dem gehosteten Skript interagiert, mit der <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> Methode und die <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> Eigenschaft. Weitere Informationen finden Sie unter [Übersicht über WPF-Add-Ins](./app-development/wpf-add-ins-overview.md).  
  
 Wenn Ihre Anwendung mit WPF verwendet <xref:System.Windows.Controls.WebBrowser> -Steuerelement, eine andere Möglichkeit, die Sicherheit erhöhen und verringern Angriffe ist, um Internet Explorer-Funktionssteuerelemente zu aktivieren. Funktionssteuerelemente sind Ergänzungen zu Internet Explorer, mit denen Administratoren und Entwicklern, konfigurieren die Features von Internet Explorer und Anwendungen, in denen das WebBrowser ActiveX-Steuerelement, das WPF <xref:System.Windows.Controls.WebBrowser> dient als Wrapper zu steuern. Funktionssteuerelemente können konfiguriert werden, mithilfe der [CoInternetSetFeatureEnabled](https://go.microsoft.com/fwlink/?LinkId=179394) Funktion oder durch Ändern der Werte in der Registrierung. Weitere Informationen zu Funktionssteuerelemente, finden Sie unter [Introduction to Feature Controls](https://go.microsoft.com/fwlink/?LinkId=179390) und [Internet Feature Control Keys](https://go.microsoft.com/fwlink/?LinkId=179392).  
  
 Wenn Sie eine eigenständige WPF-Anwendung entwickeln, die die WPF verwendet <xref:System.Windows.Controls.WebBrowser> WPF-Steuerelement, automatisch die folgenden Funktionssteuerelemente für Ihre Anwendung aktiviert.  
  
|Funktionssteuerelement|  
|---------------------|  
|FEATURE_MIME_HANDLING|  
|FEATURE_MIME_SNIFFING|  
|FEATURE_OBJECT_CACHING|  
|FEATURE_SAFE_BINDTOOBJECT|  
|FEATURE_WINDOW_RESTRICTIONS|  
|FEATURE_ZONE_ELEVATION|  
|FEATURE_RESTRICT_FILEDOWNLOAD|  
|FEATURE_RESTRICT_ACTIVEXINSTALL|  
|FEATURE_ADDON_MANAGEMENT|  
|FEATURE_HTTP_USERNAME_PASSWORD_DISABLE|  
|FEATURE_SECURITYBAND|  
|FEATURE_UNC_SAVEDFILECHECK|  
|FEATURE_VALIDATE_NAVIGATE_URL|  
|FEATURE_DISABLE_TELNET_PROTOCOL|  
|FEATURE_WEBOC_POPUPMANAGEMENT|  
|FEATURE_DISABLE_LEGACY_COMPRESSION|  
|FEATURE_SSLUX|  
  
 Da diese Funktionssteuerelemente bedingungslos aktiviert werden, können sie möglicherweise voll vertrauenswürdige Anwendungen beeinträchtigen. In diesem Fall kann das entsprechende Funktionssteuerelement deaktiviert werden, wenn kein Sicherheitsrisiko für die jeweilige Anwendung und den gehosteten Inhalt besteht.  
  
 Funktionssteuerelemente werden angewendet, durch den Prozess der WebBrowser ActiveX-Objekt instanziiert. Daher wird unbedingt empfohlen, beim Erstellen einer eigenständigen Anwendung, die zu nicht vertrauenswürdigem Inhalt navigieren kann, zusätzliche Funktionssteuerelemente zu aktivieren.  
  
> [!NOTE]
>  Diese Empfehlung basiert auf allgemeinen Empfehlungen für MSHTML- und SHDOCVW-Hostsicherheit. Weitere Informationen finden Sie unter [The MSHTML Host Security FAQ: Teil I, II](https://go.microsoft.com/fwlink/?LinkId=179396) und [der MSHTML Host Security – häufig gestellte Fragen: Teil II of II](https://go.microsoft.com/fwlink/?LinkId=179415).  
  
 Für eine ausführbare Datei sollten die folgenden Funktionssteuerelemente aktiviert werden, indem der Registrierungswert auf 1 festgelegt wird.  
  
|Funktionssteuerelement|  
|---------------------|  
|FEATURE_ACTIVEX_REPURPOSEDETECTION|  
|FEATURE_BLOCK_LMZ_IMG|  
|FEATURE_BLOCK_LMZ_OBJECT|  
|FEATURE_BLOCK_LMZ_SCRIPT|  
|FEATURE_RESTRICT_RES_TO_LMZ|  
|FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7|  
|FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG|  
|FEATURE_LOCALMACHINE_LOCKDOWN|  
|FEATURE_FORCE_ADDR_AND_STATUS|  
|FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND|  
  
 Für eine ausführbare Datei sollte das folgenden Funktionssteuerelement deaktiviert werden, indem der Registrierungswert auf 0 festgelegt wird.  
  
|Funktionssteuerelement|  
|---------------------|  
|FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT|  
  
 Wenn das Ausführen einer teilweise vertrauenswürdiges [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] , umfasst eine WPF <xref:System.Windows.Controls.WebBrowser> Steuerelement [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)], hostet WPF das WebBrowser ActiveX-Steuerelement im Adressraum des Internet Explorer-Prozesses. Da das WebBrowser ActiveX-Steuerelement, in gehostet wird der [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] verarbeiten, die alle Funktionssteuerelemente für Internet Explorer auch für das WebBrowser ActiveX-Steuerelement aktiviert sind.  
  
 XBAPs, die in Internet Explorer ausgeführt werden, haben im Vergleich zu normalen eigenständigen Anwendungen ebenfalls ein höheres Maß an Sicherheit. Diese zusätzliche Sicherheitsmaßnahme ist, da Internet Explorer, und daher WebBrowser ActiveX-Steuerelement, ausgeführt wird im geschützten Modus wird standardmäßig auf [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] und [!INCLUDE[win7](../../../includes/win7-md.md)]. Weitere Informationen zum geschützten Modus finden Sie unter [Understanding and Working in Protected Mode Internet Explorer](https://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
>  Wenn Sie versuchen, eine XBAP auszuführen, die eine WPF enthält <xref:System.Windows.Controls.WebBrowser> -Steuerelement in Firefox in der Internetzone eine <xref:System.Security.SecurityException> ausgelöst. Dies geschieht aufgrund der WPF-Sicherheitsrichtlinie.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Deaktivieren von APTCA-Assemblys für teilweise vertrauenswürdige Clientanwendungen  
 Wenn verwaltete Assemblys installiert sind, in der [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)], werden sie voll vertrauenswürdig, da der Benutzer für die Installation eine explizite Berechtigung bereitstellen muss. Da sie voll vertrauenswürdig sind, können sie nur von voll vertrauenswürdigen verwalteten Clientanwendungen verwendet werden. Um deren Verwendung durch teilweise vertrauenswürdigen Anwendungen zu ermöglichen, müssen sie mit markiert werden die <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Mit diesem Attribut sollten nur Assemblys markiert werden, für die bei Tests nachgewiesen wurde, dass sie bei Ausführung in teilweiser Vertrauenswürdigkeit sicher sind.  
  
 Es ist jedoch möglich, dass eine APTCA-Assembly, die ein Sicherheitsrisiko zeigen, nach der Installation in der [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)]. Nachdem ein Sicherheitsrisiko entdeckt wurde, können Assemblyherausgeber ein Sicherheitsupdate erstellen, um das Problem in vorhandenen Installationen zu beheben und Installationen zu schützen, die nach der Entdeckung des Problems erfolgen. Eine Option für ein solches Update besteht darin, die Assembly zu deinstallieren, was jedoch zum Versagen anderer voll vertrauenswürdiger Clientanwendungen führen kann, die diese Assembly verwenden.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Stellt einen Mechanismus, mit dem eine APTCA-Assembly deaktiviert werden, kann für teilweise vertrauenswürdige [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] ohne die APTCA-Assembly zu deinstallieren.  
  
 Um eine APTCA-Assembly zu deaktivieren, müssen Sie einen speziellen Registrierungsschlüssel erstellen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Es folgt ein Beispiel:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Dieser Schlüssel erstellt einen Eintrag für die APTCA-Assembly. Sie müssen außerdem einen Wert in diesem Schlüssel erstellen, der die Assembly aktiviert oder deaktiviert. Die Details des Werts sehen wie folgt aus:  
  
-   Wertname: **APTCA_FLAG**.  
  
-   Werttyp: **REG_DWORD**.  
  
-   Wertdaten: **1** = deaktivieren; **0** zu aktivieren.  
  
 Muss eine Assembly für teilweise vertrauenswürdige Clientanwendungen deaktiviert werden, können Sie ein Update schreiben, in dem der Registrierungsschlüssel und dessen Wert aktualisiert werden.  
  
> [!NOTE]
>  Core, .NET Framework-Assemblys sind nicht betroffen, indem sie auf diese Weise deaktiviert, da sie für die Ausführung von verwalteten Anwendungen erforderlich sind. Die Unterstützung zur Deaktivierung von APTCA-Assemblys zielt hauptsächlich auf Anwendungen von Drittanbietern ab.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Sandkastenverhalten für Loose XAML-Dateien  
 Lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien sind nur-Markup-XAML-Dateien, die nicht auf alle Code-Behind, Ereignishandler- oder anwendungsspezifischen Assembly abhängen. Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien direkt aus dem Browser navigiert, die sie in einem Sicherheitssandkasten basierend auf den Standardberechtigungssatz für die Zone geladen werden.  
  
 Das Sicherheitsverhalten ist jedoch anders, wenn Sie loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien aus navigiert wird, werden eine <xref:System.Windows.Navigation.NavigationWindow> oder <xref:System.Windows.Controls.Frame> in einer eigenständigen Anwendung.  
  
 In beiden Fällen die loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Datei, die zu dem navigiert wird erbt die Berechtigungen ihrer hostanwendung. Allerdings kann dieses Verhalten hinsichtlich der Sicherheit nicht wünschenswert, besonders wenn eine loose sein [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Datei erzeugt wurde, indem Sie eine Entität, die nicht vertrauenswürdig oder unbekannt ist. Diese Art von Inhalt wird als bezeichnet *externe Inhalte*, und beide <xref:System.Windows.Controls.Frame> und <xref:System.Windows.Navigation.NavigationWindow> kann konfiguriert werden, um ihn bei der Navigation zu isolieren. Isolation ist erreicht, indem die **SandboxExternalContent** Eigenschaft auf "true" in den folgenden Beispielen für dargestellt, <xref:System.Windows.Controls.Frame> und <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Mit dieser Einstellung wird der externe Inhalt in einen Prozess geladen, der von dem Prozess getrennt ist, der die Anwendung hostet. Dieser Prozess ist auf den Standardberechtigungssatz für die Internetzone beschränkt, wodurch er effizient von der Hostanwendung und dem Clientcomputer isoliert ist.  
  
> [!NOTE]
>  Obwohl Navigation zu loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien entweder eine <xref:System.Windows.Navigation.NavigationWindow> oder <xref:System.Windows.Controls.Frame> in einer eigenständigen Anwendung implementiert wird basierend auf der WPF-Browserhostinginfrastruktur im Zusammenhang mit den PresentationHost-Prozess, die Sicherheitsstufe wird etwas niedriger, als wenn der Inhalt auf direkt in Internet Explorer geladen wird [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] und [!INCLUDE[win7](../../../includes/win7-md.md)] (Was wäre immer noch über PresentationHost). Dies liegt daran, dass eine eigenständige WPF-Anwendung, die einen Webbrowser verwendet, die zusätzliche „Geschützter Modus“-Sicherheitsfunktion von Internet Explorer nicht bereitstellt.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ressourcen zum Entwickeln von WPF-Anwendungen, die die Sicherheit erhöhen  
 Im folgenden sind einige zusätzlichen Ressourcen zur Entwicklung [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Anwendungen, die Sicherheit erhöhen:  
  
|Bereich|Ressource|  
|----------|--------------|  
|Verwalteter Code|[Patterns and Practices-Sicherheitsleitfaden für Anwendungen](https://go.microsoft.com/fwlink/?LinkId=117426)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[Codezugriffssicherheit](../misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Siehe auch

- [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
- [Patterns and Practices-Sicherheitsleitfaden für Anwendungen](https://go.microsoft.com/fwlink/?LinkId=117426)
- [Codezugriffssicherheit](../misc/code-access-security.md)
- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
- [Übersicht über XAML (WPF)](./advanced/xaml-overview-wpf.md)
