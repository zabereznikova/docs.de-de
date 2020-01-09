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
ms.openlocfilehash: 612b99354310c18030cefce4e6f02fab8ed20f83
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636769"
---
# <a name="security-wpf"></a>Sicherheit (WPF)
<a name="introduction"></a>Beim Entwickeln von eigenständigen und im Browser gehosteten Anwendungen für Windows Presentation Foundation (WPF) müssen Sie das Sicherheitsmodell in Erwägung gezogen. Eigenständige WPF-Anwendungen werden mit uneingeschränkten Berechtigungen (CAS**FullTrust** -Berechtigungs Satz) ausgeführt, unabhängig davon, ob Sie mit Windows Installer (MSI), xcopy oder ClickOnce bereitgestellt werden. Die Bereitstellung teilweise vertrauenswürdiger eigenständiger WPF-Anwendungen mit ClickOnce wird nicht unterstützt. Allerdings kann eine voll vertrauenswürdige Host Anwendung eine teilweise vertrauenswürdige <xref:System.AppDomain> mithilfe des .NET Framework Add-in-Modells erstellen. Weitere Informationen finden Sie unter [Übersicht über WPF-Add-ins](./app-development/wpf-add-ins-overview.md).  
  
 Im Browser gehostete WPF-Anwendungen werden von Windows Internet Explorer oder Firefox gehostet und können entweder XAML-Browser Anwendungen (XBAPs) oder lose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] Dokumente sein. Weitere Informationen finden Sie unter [Übersicht über WPF-XAML-Browser Anwendungen](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 Im Browser gehostete WPF-Anwendungen werden standardmäßig in einer teilweise vertrauenswürdigen Sicherheits Sandbox ausgeführt, die auf den Standard Berechtigungs Satz der CAS-**Internet** Zone beschränkt ist. Dadurch werden vom Browser gehostete WPF-Anwendungen praktisch auf die gleiche Weise isoliert, wie Sie davon ausgehen, dass typische Webanwendungen isoliert sind. Eine XBAP kann, abhängig von der Sicherheitszone der Bereitstellungs-URL und der Sicherheitskonfiguration des Clients, Berechtigungen bis zur vollen Vertrauenswürdigkeit erhöhen. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md).  
  
 In diesem Thema wird das Sicherheitsmodell für eigenständige und im Browser gehostete WPF-Anwendungen (Windows Presentation Foundation) erläutert.  
  
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
  
 Als *Anwendungsnavigation* wird die Navigation zwischen Inhaltselementen in einer Anwendung bezeichnet, die in einem Browser gehostet wird. Als *Browsernavigation* wird die Navigation bezeichnet, die die Inhalts- und Speicherort-URL eines Browsers selbst ändert. Die Beziehung zwischen Anwendungs Navigation (normalerweise XAML) und Browser Navigation (in der Regel HTML) wird in der folgenden Abbildung dargestellt:
  
 ![Beziehung zwischen Anwendungs Navigation und Browser Navigation.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Der Inhaltstyp, der für eine XBAP als sicher eingestuft wird, hängt in erster Linie davon ab, ob die Anwendungs Navigation oder Browser Navigation verwendet wird.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Sicherheit von Anwendungsnavigation  
 Die Anwendungs Navigation wird als sicher betrachtet, wenn Sie mit einem Paket-URI identifiziert werden kann, der vier Inhaltstypen unterstützt:  
  
|Inhaltstyp|Beschreibung|URI-Beispiel|  
|------------------|-----------------|-----------------|  
|Ressource|Dateien, die einem Projekt mit dem Buildtyp **Ressource**hinzugefügt werden.|`pack://application:,,,/MyResourceFile.xaml`|  
|Inhalt|Dateien, die einem Projekt mit dem Buildtyp **Inhalt**hinzugefügt werden.|`pack://application:,,,/MyContentFile.xaml`|  
|Ursprungswebsite|Dateien, die einem Projekt mit dem Buildtyp " **keine**" hinzugefügt werden.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Anwendungscode|XAML-Ressourcen mit kompiliertem Code-Behind<br /><br /> \- oder -<br /><br /> XAML-Dateien, die einem Projekt mit dem Buildtyp **Page**hinzugefügt werden.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Weitere Informationen zu Anwendungs Datendateien und Paket-URIs finden Sie unter [WPF-Anwendungs Ressource, Inhalts-und Datendateien](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 Ein Navigieren zu Dateien dieser Inhaltstypen kann sowohl durch einen Benutzer als auch programmgesteuert erfolgen:  
  
- **Benutzernavigation**. Der Benutzer navigiert, indem er auf ein <xref:System.Windows.Documents.Hyperlink> Element klickt.  
  
- **Programmgesteuerte Navigation** Die Anwendung navigiert, ohne den Benutzer einzubeziehen, z. b. durch Festlegen der <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>-Eigenschaft.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Sicherheit von Browsernavigation  
 Browsernavigation wird nur unter den folgenden Bedingungen als sicher betrachtet:  
  
- **Benutzernavigation**. Der Benutzer navigiert, indem er auf ein <xref:System.Windows.Documents.Hyperlink> Element klickt, das sich innerhalb des Haupt <xref:System.Windows.Navigation.NavigationWindow>befindet, nicht in einem geschachtelten <xref:System.Windows.Controls.Frame>.  
  
- **Zone**. Der Inhalt, in dem navigiert wird, befindet sich im Internet oder im lokalen Intranet.  
  
- **Protokoll**. Das verwendete Protokoll ist entweder **http**, **https**, **File**oder **mailto**.  
  
 Wenn eine XBAP versucht, auf eine Weise zu Inhalten zu navigieren, die diese Bedingungen nicht erfüllt, wird eine <xref:System.Security.SecurityException> ausgelöst.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Sicherheitseinstellungen für webbrowsende Software  
 Die Sicherheitseinstellungen auf dem Computer bestimmen, welcher Zugriff jeder webbrowsenden Software gewährt wird. Die Webbrowsersoftware umfasst alle Anwendungen oder Komponenten, die die [WinInet](/windows/win32/wininet/portal) -oder [URLMON](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) -APIs verwenden, einschließlich Internet Explorer und PresentationHost. exe.  
  
 Internet Explorer bietet einen Mechanismus, mit dem Sie die Funktionalität konfigurieren können, die von oder aus Internet Explorer ausgeführt werden darf, einschließlich der folgenden:  
  
- .NET Framework abhängige Komponenten  
  
- ActiveX-Steuerelemente und Plug-Ins  
  
- Downloads  
  
- Skripts  
  
- Benutzerauthentifizierung  
  
 Die Sammlung von Funktionen, die auf diese Weise gesichert werden können, wird für die Zonen **Internet**, **Intranet**, **Vertrauenswürdige Sites**und **Eingeschränkte Sites** pro Zone konfiguriert. Die folgenden Schritte beschreiben, wie die Sicherheitseinstellungen konfiguriert werden:  
  
1. Öffnen Sie die **Systemsteuerung**.  
  
2. Klicken Sie auf **Netzwerk und Internet** , und klicken Sie dann auf **Internetoptionen**.  
  
     Das Dialogfeld "Internetoptionen" wird angezeigt.  
  
3. Wählen Sie auf der Registerkarte **Sicherheit** die Zone aus, für die Sie die Sicherheitseinstellungen konfigurieren möchten.  
  
4. Klicken Sie auf die Schaltfläche **benutzerdefinierte Ebene** .  
  
     Das Dialogfeld **Sicherheitseinstellungen** wird angezeigt, und Sie können die Sicherheitseinstellungen für die ausgewählte Zone konfigurieren.  
  
     ![Screenshot, der das Dialogfeld "Sicherheitseinstellungen" anzeigt.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> Sie können auch aus Internet Explorer zum Dialogfeld „Internetoptionen“ gelangen. Klicken Sie auf **Extras und dann auf** **Internet Optionen**.  
  
 Ab Windows Internet Explorer 7 sind die folgenden Sicherheitseinstellungen speziell für .NET Framework enthalten:  
  
- **Loose XAML**. Steuert, ob Internet Explorer zu [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien navigieren und diese verlieren kann. (Optionen „Aktivieren“, „Deaktivieren“ und „Bestätigen“.)  
  
- **XAML-Browseranwendungen**. Steuert, ob Internet Explorer zu XBAPs navigieren und diese ausführen kann. (Optionen „Aktivieren“, „Deaktivieren“ und „Bestätigen“.)  
  
 Standardmäßig sind diese Einstellungen für die Zonen " **Internet**", " **Lokales Intranet**" und " **Vertrauenswürdige Sites** " aktiviert und für die Zone der **eingeschränkten Sites** deaktiviert.  
  
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
 Das WPF-<xref:System.Windows.Controls.WebBrowser> Steuerelement kann zum Hosten von Webinhalt verwendet werden. Die WPF-<xref:System.Windows.Controls.WebBrowser> Steuerung umschließt das zugrunde liegende WebBrowser-ActiveX-Steuerelement. WPF bietet Unterstützung für das Sichern Ihrer Anwendung, wenn Sie das WPF-<xref:System.Windows.Controls.WebBrowser>-Steuerelement zum Hosten von nicht vertrauenswürdigem Webinhalt verwenden. Einige Sicherheitsfeatures müssen jedoch direkt durch die Anwendungen angewendet werden, die das <xref:System.Windows.Controls.WebBrowser>-Steuerelement verwenden. Weitere Informationen zum WebBrowser-ActiveX-Steuerelement finden Sie unter [WebBrowser-Steuerelement Übersichten und Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85)).  
  
> [!NOTE]
> Dieser Abschnitt gilt auch für das <xref:System.Windows.Controls.Frame>-Steuerelement, da es die <xref:System.Windows.Controls.WebBrowser> verwendet, um zu HTML-Inhalten zu navigieren.  
  
 Wenn das WPF-<xref:System.Windows.Controls.WebBrowser>-Steuerelement zum Hosten von nicht vertrauenswürdigem Webinhalt verwendet wird, sollte Ihre Anwendung eine teilweise vertrauenswürdige <xref:System.AppDomain> verwenden, um den Anwendungscode vor potenziell schädlichem HTML-Skriptcode zu isolieren. Dies trifft vor allem dann zu, wenn Ihre Anwendung mit dem gehosteten Skript interagiert, indem Sie die <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A>-Methode und die <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>-Eigenschaft verwendet. Weitere Informationen finden Sie unter [Übersicht über WPF-Add-ins](./app-development/wpf-add-ins-overview.md).  
  
 Wenn Ihre Anwendung das WPF-<xref:System.Windows.Controls.WebBrowser> Steuerelement verwendet, besteht eine weitere Möglichkeit zur Erhöhung der Sicherheit und Entschärfung von Angriffen darin, Internet Explorer-Funktions Steuerelemente zu aktivieren Funktions Steuerelemente sind Ergänzungen zu Internet Explorer, mit denen Administratoren und Entwickler Funktionen von Internet Explorer und Anwendungen konfigurieren können, die das WebBrowser-ActiveX-Steuerelement hosten, das von der WPF-<xref:System.Windows.Controls.WebBrowser> Steuerung umschlossen wird. Funktions Steuerelemente können mithilfe der [cointernetsetfeatureaktivierten](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) Funktion oder durch Ändern von Werten in der Registrierung konfiguriert werden. Weitere Informationen zu Funktions Steuerelementen finden [Sie unter Einführung in Funktions Steuerelemente](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) und [Internet Funktions Steuerelemente](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85)).  
  
 Wenn Sie eine eigenständige WPF-Anwendung entwickeln, die das WPF-<xref:System.Windows.Controls.WebBrowser> Steuerelement verwendet, aktiviert WPF automatisch die folgenden Featuresteuerelemente für Ihre Anwendung.  
  
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
  
 Funktions Steuerelemente werden durch den Prozess angewendet, der das WebBrowser-ActiveX-Objekt instanziiert. Daher wird unbedingt empfohlen, beim Erstellen einer eigenständigen Anwendung, die zu nicht vertrauenswürdigem Inhalt navigieren kann, zusätzliche Funktionssteuerelemente zu aktivieren.  
  
> [!NOTE]
> Diese Empfehlung basiert auf allgemeinen Empfehlungen für MSHTML- und SHDOCVW-Hostsicherheit. Weitere Informationen finden Sie in den häufig gestellten Fragen [zur Sicherheit des MSHTML-Hosts: Teil I von II](https://msrc-blog.microsoft.com/archive/2009/04/02/the-mshtml-host-security-faq.aspx) und [MSHTML Host Security FAQ: Part II of II](https://msrc-blog.microsoft.com/archive/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii.aspx).  
  
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
  
 Wenn Sie eine teilweise vertrauenswürdige XAML-Browser Anwendung (XBAP) ausführen, die ein WPF-<xref:System.Windows.Controls.WebBrowser>-Steuerelement in Windows Internet Explorer enthält, hostet WPF das WebBrowser-ActiveX-Steuerelement im Adressraum des Internet Explorer-Prozesses. Da das WebBrowser-ActiveX-Steuerelement im Internet Explorer-Prozess gehostet wird, sind alle Featuresteuerelemente für Internet Explorer auch für das WebBrowser-ActiveX-Steuerelement aktiviert.  
  
 XBAPs, die in Internet Explorer ausgeführt werden, haben im Vergleich zu normalen eigenständigen Anwendungen ebenfalls ein höheres Maß an Sicherheit. Diese zusätzliche Sicherheit besteht darin, dass Internet Explorer und somit das WebBrowser-ActiveX-Steuerelement unter Windows Vista und Windows 7 standardmäßig im geschützten Modus ausgeführt wird. Weitere Informationen zum geschützten Modus finden Sie unter [Understanding and working in Protected Mode Internet Explorer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/).  
  
> [!NOTE]
> Wenn Sie versuchen, eine XBAP auszuführen, die ein WPF-<xref:System.Windows.Controls.WebBrowser>-Steuerelement in Firefox enthält, wird in der Internet Zone ein <xref:System.Security.SecurityException> ausgelöst. Dies geschieht aufgrund der WPF-Sicherheitsrichtlinie.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Deaktivieren von APTCA-Assemblys für teilweise vertrauenswürdige Clientanwendungen  
 Wenn verwaltete Assemblys im globalen Assemblycache (Global Assembly Cache, GAC) installiert werden, werden Sie vollständig vertrauenswürdig, da der Benutzer explizite Berechtigungen zur Installation bereitstellen muss. Da sie voll vertrauenswürdig sind, können sie nur von voll vertrauenswürdigen verwalteten Clientanwendungen verwendet werden. Damit Sie von teilweise vertrauenswürdigen Anwendungen verwendet werden können, müssen Sie mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) gekennzeichnet werden. Mit diesem Attribut sollten nur Assemblys markiert werden, für die bei Tests nachgewiesen wurde, dass sie bei Ausführung in teilweiser Vertrauenswürdigkeit sicher sind.  
  
 Es ist jedoch möglich, dass eine APTCA-Assembly nach der Installation im GAC einen Sicherheitsfehler aufweist. Nachdem ein Sicherheitsrisiko entdeckt wurde, können Assemblyherausgeber ein Sicherheitsupdate erstellen, um das Problem in vorhandenen Installationen zu beheben und Installationen zu schützen, die nach der Entdeckung des Problems erfolgen. Eine Option für ein solches Update besteht darin, die Assembly zu deinstallieren, was jedoch zum Versagen anderer voll vertrauenswürdiger Clientanwendungen führen kann, die diese Assembly verwenden.  
  
 WPF bietet einen Mechanismus, mit dem eine APTCA-Assembly für teilweise vertrauenswürdige XBAPs deaktiviert werden kann, ohne die APTCA-Assembly zu deinstallieren.  
  
 Um eine APTCA-Assembly zu deaktivieren, müssen Sie einen speziellen Registrierungsschlüssel erstellen:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Es folgt ein Beispiel:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Dieser Schlüssel erstellt einen Eintrag für die APTCA-Assembly. Sie müssen außerdem einen Wert in diesem Schlüssel erstellen, der die Assembly aktiviert oder deaktiviert. Die Details des Werts sehen wie folgt aus:  
  
- Wertname: **APTCA_FLAG**.  
  
- Werttyp: **REG_DWORD**.  
  
- Wertdaten: **1** zum Deaktivieren; **0** zum Aktivieren.  
  
 Muss eine Assembly für teilweise vertrauenswürdige Clientanwendungen deaktiviert werden, können Sie ein Update schreiben, in dem der Registrierungsschlüssel und dessen Wert aktualisiert werden.  
  
> [!NOTE]
> Core .NET Framework Assemblys sind nicht betroffen, da Sie auf diese Weise deaktiviert werden, da Sie für die Durchführung verwalteter Anwendungen erforderlich sind. Die Unterstützung zur Deaktivierung von APTCA-Assemblys zielt hauptsächlich auf Anwendungen von Drittanbietern ab.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Sandkastenverhalten für Loose XAML-Dateien  
 Lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien sind nur-Markup-XAML-Dateien, die von keinen Code-Behind-, Ereignishandler-oder anwendungsspezifischen Assemblys abhängen. Wenn lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien direkt über den Browser navigiert werden, werden Sie auf Grundlage des Standard Berechtigungs Satzes für die Internet Zone in eine Sicherheits Sandbox geladen.  
  
 Das Sicherheits Verhalten unterscheidet sich jedoch, wenn Lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien entweder aus einem <xref:System.Windows.Navigation.NavigationWindow> oder <xref:System.Windows.Controls.Frame> in einer eigenständigen Anwendung navigiert werden.  
  
 In beiden Fällen erbt die lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Datei, zu der navigiert wird, die Berechtigungen Ihrer Host Anwendung. Dieses Verhalten kann jedoch aus Sicherheitsgründen nicht erwünscht sein, insbesondere dann, wenn eine lose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Datei von einer nicht vertrauenswürdigen oder unbekannten Entität erzeugt wurde. Dieser Inhaltstyp wird als *externer Inhalt*bezeichnet, und sowohl <xref:System.Windows.Controls.Frame> als auch <xref:System.Windows.Navigation.NavigationWindow> können so konfiguriert werden, dass Sie bei der Navigation zu isoliert werden. Die Isolation wird erreicht, indem die **SandboxExternalContent** -Eigenschaft auf true festgelegt wird, wie in den folgenden Beispielen für <xref:System.Windows.Controls.Frame> und <xref:System.Windows.Navigation.NavigationWindow>gezeigt:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Mit dieser Einstellung wird der externe Inhalt in einen Prozess geladen, der von dem Prozess getrennt ist, der die Anwendung hostet. Dieser Prozess ist auf den Standardberechtigungssatz für die Internetzone beschränkt, wodurch er effizient von der Hostanwendung und dem Clientcomputer isoliert ist.  
  
> [!NOTE]
> Obwohl die Navigation zu losen [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Dateien aus einem <xref:System.Windows.Navigation.NavigationWindow> oder <xref:System.Windows.Controls.Frame> in einer eigenständigen Anwendung basierend auf der WPF-Browser-Hostinginfrastruktur implementiert ist, die den PresentationHost-Prozess beinhaltet, ist die Sicherheitsstufe etwas kleiner als der Inhalt, der direkt in Internet Explorer unter Windows Vista und Windows 7 geladen wird (was noch über PresentationHost erfolgt). Dies liegt daran, dass eine eigenständige WPF-Anwendung, die einen Webbrowser verwendet, die zusätzliche „Geschützter Modus“-Sicherheitsfunktion von Internet Explorer nicht bereitstellt.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ressourcen zum Entwickeln von WPF-Anwendungen, die die Sicherheit erhöhen  
 Im folgenden finden Sie einige zusätzliche Ressourcen zum Entwickeln von WPF-Anwendungen, die die Sicherheit erhöhen:  
  
|Fläche|Ressource|  
|----------|--------------|  
|Verwalteter Code|[Sicherheits Leit Faden zu Mustern und Vorgehensweisen für Anwendungen](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[Codezugriffssicherheit](../misc/code-access-security.md)|  
|ClickOnce|[ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Siehe auch

- [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](wpf-partial-trust-security.md)
- [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
- [Sicherheits Leit Faden zu Mustern und Vorgehensweisen für Anwendungen](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [Codezugriffssicherheit](../misc/code-access-security.md)
- [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
