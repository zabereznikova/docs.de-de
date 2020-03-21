---
title: Sicherheit
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
ms.openlocfilehash: e0a56dcbf8d151fcb0d4f6271ecba15c0ff955a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174614"
---
# <a name="security-wpf"></a>Sicherheit (WPF)
<a name="introduction"></a>Beim Entwickeln von Windows Presentation Foundation (WPF)-Einzel- und browsergehosteten Anwendungen müssen Sie das Sicherheitsmodell berücksichtigen. Eigenständige WPF-Anwendungen werden mit uneingeschränkten Berechtigungen (CAS FullTrust-Berechtigungssatz) ausgeführt, unabhängig davon, ob sie mit Windows Installer (.msi), XCopy oder ClickOnce bereitgestellt werden.**FullTrust** Die Bereitstellung teilweise vertrauenswürdiger eigenständiger WPF-Anwendungen mit ClickOnce wird nicht unterstützt. Eine Hostanwendung mit voller Vertrauenswürdigkeit kann <xref:System.AppDomain> jedoch mithilfe des .NET Framework-Add-In-Modells eine teilweise Vertrauensstellung erstellen. Weitere Informationen finden Sie unter [WPF Add-Ins Overview](./app-development/wpf-add-ins-overview.md).  
  
 WPF-Browser-gehostete Anwendungen werden von Windows Internet Explorer oder Firefox gehostet und können entweder [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] XAML-Browseranwendungen (XBAPs) oder lose Dokumente sein. Weitere Informationen finden Sie unter [WPF XAML Browser Applications Overview](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 WPF-Browser-gehostete Anwendungen werden standardmäßig in einer teilweise vertrauenswürdigen Sicherheitssandbox ausgeführt, die auf den standardmäßigen BERECHTIGUNGssatz für**CAS-Internetzonen** beschränkt ist. Dadurch werden vom Browser gehostete WPF-Anwendungen auf die gleiche Weise vom Clientcomputer isoliert, wie Sie erwarten würden, dass typische Webanwendungen isoliert werden. Eine XBAP kann, abhängig von der Sicherheitszone der Bereitstellungs-URL und der Sicherheitskonfiguration des Clients, Berechtigungen bis zur vollen Vertrauenswürdigkeit erhöhen. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md).  
  
 In diesem Thema wird das Sicherheitsmodell für Windows Presentation Foundation (WPF)-Einzel- und browsergehostete Anwendungen erläutert.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Sichere Navigation](#SafeTopLevelNavigation)  
  
- [Sicherheitseinstellungen für webbrowsende Software](#InternetExplorerSecuritySettings)  
  
- [WebBrowser-Steuerelement und Funktionssteuerelemente](#webbrowser_control_and_feature_controls)  
  
- [Deaktivieren von APTCA-Assemblys für teilweise vertrauenswürdige Clientanwendungen](#APTCA)  
  
- [Sandkastenverhalten für Loose XAML-Dateien](#LooseContentSandboxing)  
  
- [Ressourcen zum Entwickeln von WPF-Anwendungen, die die Sicherheit erhöhen](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>
## <a name="safe-navigation"></a>Sichere Navigation  
 Bei XBAPs unterscheidet WPF zwei Arten der Navigation: Anwendung und Browser.  
  
 Als *Anwendungsnavigation* wird die Navigation zwischen Inhaltselementen in einer Anwendung bezeichnet, die in einem Browser gehostet wird. Als *Browsernavigation* wird die Navigation bezeichnet, die die Inhalts- und Speicherort-URL eines Browsers selbst ändert. Die Beziehung zwischen Anwendungsnavigation (in der Regel XAML) und Browsernavigation (in der Regel HTML) wird in der folgenden Abbildung dargestellt:
  
 ![Beziehung zwischen Anwendungsnavigation und Browsernavigation.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Der Inhaltstyp, der als sicher für einen XBAP zum Navigieren gilt, hängt in erster Linie davon ab, ob die Anwendungsnavigation oder die Browsernavigation verwendet wird.  
  
<a name="Application_Navigation_Security"></a>
### <a name="application-navigation-security"></a>Sicherheit von Anwendungsnavigation  
 Die Anwendungsnavigation gilt als sicher, wenn sie mit einem Pack-URI identifiziert werden kann, der vier Inhaltstypen unterstützt:  
  
|Inhaltstyp|Beschreibung|URI-Beispiel|  
|------------------|-----------------|-----------------|  
|Resource|Dateien, die einem Projekt mit dem Buildtyp **Resource**hinzugefügt werden.|`pack://application:,,,/MyResourceFile.xaml`|  
|Inhalt|Dateien, die einem Projekt mit dem Buildtyp **Inhalt**hinzugefügt werden.|`pack://application:,,,/MyContentFile.xaml`|  
|Ursprungswebsite|Dateien, die einem Projekt mit dem Buildtyp **Keine**hinzugefügt werden.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Anwendungscode|XAML-Ressourcen mit kompiliertem Code-Behind<br /><br /> Oder<br /><br /> XAML-Dateien, die einem Projekt mit dem Buildtyp **Page**hinzugefügt werden.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Weitere Informationen zu Anwendungsdatendateien und Pack-URIs finden Sie unter [WPF-Anwendungsressource, Inhalt und Datendateien](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 Ein Navigieren zu Dateien dieser Inhaltstypen kann sowohl durch einen Benutzer als auch programmgesteuert erfolgen:  
  
- **Benutzernavigation**. Der Benutzer navigiert, <xref:System.Windows.Documents.Hyperlink> indem er auf ein Element klickt.  
  
- **Programmgesteuerte Navigation** Die Anwendung navigiert, ohne den Benutzer <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> einzubeziehen, z. B. durch Festlegen der Eigenschaft.  
  
<a name="Browser_Navigation_Security"></a>
### <a name="browser-navigation-security"></a>Sicherheit von Browsernavigation  
 Browsernavigation wird nur unter den folgenden Bedingungen als sicher betrachtet:  
  
- **Benutzernavigation**. Der Benutzer navigiert, <xref:System.Windows.Documents.Hyperlink> indem er auf <xref:System.Windows.Navigation.NavigationWindow>ein Element innerhalb <xref:System.Windows.Controls.Frame>der Haupt- und nicht auf eine geschachtelte element tastet.  
  
- **Zone**: Der Inhalt, in dem navigiert wird, befindet sich im Internet oder im lokalen Intranet.  
  
- **Protokoll**. Das verwendete Protokoll ist entweder **http**, **https**, **file**oder **mailto**.  
  
 Wenn ein XBAP versucht, auf eine Weise zu Inhalten zu <xref:System.Security.SecurityException> navigieren, die diesen Bedingungen nicht entspricht, wird eine ausgelöst.  
  
<a name="InternetExplorerSecuritySettings"></a>
## <a name="web-browsing-software-security-settings"></a>Sicherheitseinstellungen für webbrowsende Software  
 Die Sicherheitseinstellungen auf dem Computer bestimmen, welcher Zugriff jeder webbrowsenden Software gewährt wird. Webbrowsing-Software umfasst alle Anwendungen oder Komponenten, die die [WinINet-](/windows/win32/wininet/portal) oder [UrlMon-APIs](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) verwenden, einschließlich Internet Explorer und PresentationHost.exe.  
  
 Internet Explorer stellt einen Mechanismus bereit, mit dem Sie die Funktionalität konfigurieren können, die von oder von Internet Explorer ausgeführt werden darf, einschließlich der folgenden:  
  
- .NET Framework-abhängige Komponenten  
  
- ActiveX-Steuerelemente und Plug-Ins  
  
- Downloads  
  
- Skripterstellung  
  
- Benutzerauthentifizierung  
  
 Die Auflistung der Funktionen, die auf diese Weise gesichert werden können, wird pro Zone für die Zonen **Internet**, **Intranet**, **Vertrauenswürdige Sites**und **eingeschränkte Sites** konfiguriert. Die folgenden Schritte beschreiben, wie die Sicherheitseinstellungen konfiguriert werden:  
  
1. Öffnen Sie **die Systemsteuerung**.  
  
2. Klicken Sie auf **Netzwerk und Internet,** und klicken Sie dann auf **Internetoptionen**.  
  
     Das Dialogfeld "Internetoptionen" wird angezeigt.  
  
3. Wählen Sie auf der Registerkarte **Sicherheit** die Zone aus, für die die Sicherheitseinstellungen konfiguriert werden sollen.  
  
4. Klicken Sie auf die Schaltfläche **Benutzerdefinierte Ebene.**  
  
     Das Dialogfeld **Sicherheitseinstellungen** wird angezeigt, und Sie können die Sicherheitseinstellungen für die ausgewählte Zone konfigurieren.  
  
     ![Screenshot, der das Dialogfeld Sicherheitseinstellungen anzeigt.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> Sie können auch aus Internet Explorer zum Dialogfeld „Internetoptionen“ gelangen. Klicken Sie auf **Extras** und dann auf **Internetoptionen**.  
  
 Ab Windows Internet Explorer 7 sind die folgenden Sicherheitseinstellungen speziell für .NET Framework enthalten:  
  
- **Loose XAML**. Steuert, ob Internet Explorer [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] zu Dateien navigieren und diese verlieren kann. (Optionen „Aktivieren“, „Deaktivieren“ und „Bestätigen“.)  
  
- **XAML-Browseranwendungen**. Steuert, ob Internet Explorer zu XBAPs navigieren und diese ausführen kann. (Optionen „Aktivieren“, „Deaktivieren“ und „Bestätigen“.)  
  
 Standardmäßig sind diese Einstellungen alle für die Zonen **Internet**, **Lokales Intranet**und **vertrauenswürdige Sites** aktiviert und für die Zone **"Eingeschränkte Sites"** deaktiviert.  
  
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
 Das WPF-Steuerelement <xref:System.Windows.Controls.WebBrowser> kann zum Hosten von Webinhalten verwendet werden. Das WPF-Steuerelement <xref:System.Windows.Controls.WebBrowser> umschließt das zugrunde liegende WebBrowser ActiveX-Steuerelement. WPF bietet Unterstützung zum Sichern Ihrer Anwendung, <xref:System.Windows.Controls.WebBrowser> wenn Sie das WPF-Steuerelement zum Hosten nicht vertrauenswürdiger Webinhalte verwenden. Einige Sicherheitsfeatures müssen jedoch direkt von den <xref:System.Windows.Controls.WebBrowser> Anwendungen mithilfe des Steuerelements angewendet werden. Weitere Informationen zum WebBrowser ActiveX-Steuerelement finden Sie unter [WebBrowser-Steuerelementübersichten und Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85)).  
  
> [!NOTE]
> Dieser Abschnitt gilt <xref:System.Windows.Controls.Frame> auch für das <xref:System.Windows.Controls.WebBrowser> Steuerelement, da es die zum Navigieren zu HTML-Inhalten verwendet.  
  
 Wenn das <xref:System.Windows.Controls.WebBrowser> WPF-Steuerelement zum Hosten nicht vertrauenswürdiger Webinhalte <xref:System.AppDomain> verwendet wird, sollte Ihre Anwendung eine teilweise Vertrauensstellung verwenden, um Ihren Anwendungscode von potenziell schädlichem HTML-Skriptcode zu isolieren. Dies gilt insbesondere, wenn Ihre Anwendung mit dem <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> gehosteten <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> Skript interagiert, indem sie die Methode und die Eigenschaft verwendet. Weitere Informationen finden Sie unter [WPF Add-Ins Overview](./app-development/wpf-add-ins-overview.md).  
  
 Wenn Ihre Anwendung das <xref:System.Windows.Controls.WebBrowser> WPF-Steuerelement verwendet, können Sie die Sicherheit erhöhen und Angriffe verringern, wenn Sie Internet Explorer-Featuresteuerelemente aktivieren. Feature-Steuerelemente sind Ergänzungen zu Internet Explorer, mit denen Administratoren und Entwickler Features von Internet Explorer <xref:System.Windows.Controls.WebBrowser> und Anwendungen konfigurieren können, die das WebBrowser ActiveX-Steuerelement hosten, um das das WPF-Steuerelement umschließt. Feature-Steuerelemente können mithilfe der [CoInternetSetFeatureEnabled-Funktion](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) oder durch Ändern von Werten in der Registrierung konfiguriert werden. Weitere Informationen zu Feature-Steuerelementen finden Sie unter [Einführung in Feature-Steuerelemente](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) und [Internetfeature-Steuerelemente](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85)).  
  
 Wenn Sie eine eigenständige WPF-Anwendung entwickeln, <xref:System.Windows.Controls.WebBrowser> die das WPF-Steuerelement verwendet, aktiviert WPF automatisch die folgenden Feature-Steuerelemente für Ihre Anwendung.  
  
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
  
 Feature-Steuerelemente werden vom Prozess instanziieren des WebBrowser ActiveX-Objekts angewendet. Daher wird unbedingt empfohlen, beim Erstellen einer eigenständigen Anwendung, die zu nicht vertrauenswürdigem Inhalt navigieren kann, zusätzliche Funktionssteuerelemente zu aktivieren.  
  
> [!NOTE]
> Diese Empfehlung basiert auf allgemeinen Empfehlungen für MSHTML- und SHDOCVW-Hostsicherheit. Weitere Informationen finden Sie unter Die häufig gestellten Fragen zu [MSHTML-Hostsicherheit: Teil I von II](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) und DIE häufig gestellten Fragen zu [MSHTML-Hostsicherheit: Teil II von II](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/).  
  
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
  
 Wenn Sie eine xAML-Browseranwendung (Part-Trust XAML-Browseranwendung, XBAP) ausführen, die ein WPF-Steuerelement <xref:System.Windows.Controls.WebBrowser> in Windows Internet Explorer enthält, hostet WPF das WebBrowser ActiveX-Steuerelement im Adressraum des Internet Explorer-Prozesses. Da das WebBrowser ActiveX-Steuerelement im Internet Explorer-Prozess gehostet wird, sind alle Featuresteuerelemente für Internet Explorer auch für das WebBrowser ActiveX-Steuerelement aktiviert.  
  
 XBAPs, die in Internet Explorer ausgeführt werden, haben im Vergleich zu normalen eigenständigen Anwendungen ebenfalls ein höheres Maß an Sicherheit. Diese zusätzliche Sicherheit besteht darin, dass Internet Explorer und damit das WebBrowser ActiveX-Steuerelement standardmäßig unter Windows Vista und Windows 7 im geschützten Modus ausgeführt werden. Weitere Informationen zum geschützten Modus finden Sie unter Grundlegendes zum Internet [Explorer im geschützten Modus](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/).  
  
> [!NOTE]
> Wenn Sie versuchen, einen XBAP auszuführen, der ein WPF-Steuerelement <xref:System.Windows.Controls.WebBrowser> <xref:System.Security.SecurityException> in Firefox enthält, wird in der Internetzone eine ausgelöst. Dies geschieht aufgrund der WPF-Sicherheitsrichtlinie.  
  
<a name="APTCA"></a>
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Deaktivieren von APTCA-Assemblys für teilweise vertrauenswürdige Clientanwendungen  
 Wenn verwaltete Assemblys im globalen Assemblycache (GAC) installiert werden, werden sie vollständig vertrauenswürdig, da der Benutzer explizite Berechtigungen zum Installieren bereitstellen muss. Da sie voll vertrauenswürdig sind, können sie nur von voll vertrauenswürdigen verwalteten Clientanwendungen verwendet werden. Damit teilweise vertrauenswürdige Anwendungen sie verwenden können, <xref:System.Security.AllowPartiallyTrustedCallersAttribute> müssen sie mit dem (APTCA) gekennzeichnet sein. Mit diesem Attribut sollten nur Assemblys markiert werden, für die bei Tests nachgewiesen wurde, dass sie bei Ausführung in teilweiser Vertrauenswürdigkeit sicher sind.  
  
 Es ist jedoch möglich, dass eine APTCA-Baugruppe nach der Installation im GAC einen Sicherheitsfehler aufweist. Nachdem ein Sicherheitsrisiko entdeckt wurde, können Assemblyherausgeber ein Sicherheitsupdate erstellen, um das Problem in vorhandenen Installationen zu beheben und Installationen zu schützen, die nach der Entdeckung des Problems erfolgen. Eine Option für ein solches Update besteht darin, die Assembly zu deinstallieren, was jedoch zum Versagen anderer voll vertrauenswürdiger Clientanwendungen führen kann, die diese Assembly verwenden.  
  
 WPF stellt einen Mechanismus bereit, mit dem eine APTCA-Assembly für teilweise vertrauenswürdige XBAPs deaktiviert werden kann, ohne die APTCA-Assembly zu deinstallieren.  
  
 Um eine APTCA-Assembly zu deaktivieren, müssen Sie einen speziellen Registrierungsschlüssel erstellen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Es folgt ein Beispiel:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Dieser Schlüssel erstellt einen Eintrag für die APTCA-Assembly. Sie müssen außerdem einen Wert in diesem Schlüssel erstellen, der die Assembly aktiviert oder deaktiviert. Die Details des Werts sehen wie folgt aus:  
  
- Wertname: **APTCA_FLAG**.  
  
- Werttyp: **REG_DWORD**.  
  
- Wertdaten: **1** zu deaktivieren; **0** zu aktivieren.  
  
 Muss eine Assembly für teilweise vertrauenswürdige Clientanwendungen deaktiviert werden, können Sie ein Update schreiben, in dem der Registrierungsschlüssel und dessen Wert aktualisiert werden.  
  
> [!NOTE]
> Core .NET Framework-Assemblys sind nicht von der deaktivierung auf diese Weise betroffen, da sie für die Ausführung verwalteter Anwendungen erforderlich sind. Die Unterstützung zur Deaktivierung von APTCA-Assemblys zielt hauptsächlich auf Anwendungen von Drittanbietern ab.  
  
<a name="LooseContentSandboxing"></a>
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Sandkastenverhalten für Loose XAML-Dateien  
 Lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien sind reine Markup-XAML-Dateien, die nicht von CodeBehind, Ereignishandler oder anwendungsspezifischer Assembly abhängen. Wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] lose Dateien direkt aus dem Browser navigiert werden, werden sie basierend auf dem Standardmäßigen Berechtigungssatz für die Internetzone in eine Sicherheitssandbox geladen.  
  
 Das Sicherheitsverhalten unterscheidet sich [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] jedoch, wenn lose Dateien <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> von einer oder in einer eigenständigen Anwendung navigiert werden.  
  
 In beiden Fällen [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] erbt die lose Datei, die navigiert wird, um die Berechtigungen ihrer Hostanwendung zu erben. Dieses Verhalten kann jedoch aus Sicherheitssicht unerwünscht sein, [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] insbesondere wenn eine lose Datei von einer Entität erstellt wurde, die entweder nicht vertrauenswürdig oder unbekannt ist. Dieser Inhaltstyp wird als *externer* <xref:System.Windows.Controls.Frame> Inhalt <xref:System.Windows.Navigation.NavigationWindow> bezeichnet und kann beide konfiguriert werden, um ihn beim Navigieren zu isolieren. Die Isolierung wird erreicht, indem die **SandboxExternalContent-Eigenschaft** auf <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow>true gesetzt wird, wie in den folgenden Beispielen für und gezeigt:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Mit dieser Einstellung wird der externe Inhalt in einen Prozess geladen, der von dem Prozess getrennt ist, der die Anwendung hostet. Dieser Prozess ist auf den Standardberechtigungssatz für die Internetzone beschränkt, wodurch er effizient von der Hostanwendung und dem Clientcomputer isoliert ist.  
  
> [!NOTE]
> Obwohl die Navigation [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] zum Verlieren <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> von Dateien aus einer oder in einer eigenständigen Anwendung basierend auf der WPF-Browserhostinginfrastruktur implementiert wird, die den PresentationHost-Prozess einbezieht, ist die Sicherheitsstufe etwas geringer als beim direkten Laden des Inhalts in Internet Explorer unter Windows Vista und Windows 7 (dies würde immer noch über PresentationHost erfolgen). Dies liegt daran, dass eine eigenständige WPF-Anwendung, die einen Webbrowser verwendet, die zusätzliche „Geschützter Modus“-Sicherheitsfunktion von Internet Explorer nicht bereitstellt.  
  
<a name="BestPractices"></a>
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ressourcen zum Entwickeln von WPF-Anwendungen, die die Sicherheit erhöhen  
 Im Folgenden finden Sie einige zusätzliche Ressourcen zur Entwicklung von WPF-Anwendungen, die die Sicherheit fördern:  
  
|Bereich|Resource|  
|----------|--------------|  
|Verwalteter Code|[Muster und Praktiken Sicherheitsleitfaden für Anwendungen](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[Codezugriffssicherheit](../misc/code-access-security.md)|  
|ClickOnce|[ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[WPF Partial Trust Security](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Weitere Informationen

- [WPF Partial Trust Security](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
- [Muster und Praktiken Sicherheitsleitfaden für Anwendungen](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [Codezugriffssicherheit](../misc/code-access-security.md)
- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
