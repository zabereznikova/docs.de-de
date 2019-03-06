---
title: WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- partial trust security [WPF]
- detecting permissions [WPF]
- security settings for Internet Explorer [WPF]
- partial trust applications [WPF], debugging
- permissions [WPF], managing
- debugging partial trust applications [WPF]
- permissions [WPF], detecting
- feature security requirements [WPF]
- managing permissions [WPF]
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
ms.openlocfilehash: c0391099d02933cb8a32a2e134dad949034138ad
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371631"
---
# <a name="wpf-partial-trust-security"></a>WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit
<a name="introduction"></a> Im Allgemeinen sollte der direkte Zugriff von Internetanwendungen auf wichtige Systemressourcen eingeschränkt werden, um böswillige Schäden zu vermeiden. In der Standardeinstellung [!INCLUDE[TLA#tla_html](../../../includes/tlasharptla-html-md.md)] und clientseitige Skriptsprachen nicht auf wichtige Systemressourcen zugreifen. Da Windows Presentation Foundation (WPF)-Browser-gehostete Anwendungen aus dem Browser gestartet werden können, müssen sie eine ähnliche Reihe von Einschränkungen entsprechen. Um diese Einschränkungen zu erzwingen [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] sowohl [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] und [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] (finden Sie unter [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)). Standardmäßig fordern im Browser gehostete Anwendungen die Internetzone [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] Satz von Berechtigungen, unabhängig davon, ob sie über das Internet, lokales Intranet oder dem lokalen Computer gestartet werden. Für Anwendungen, die nicht mit dem vollständigen, sondern einem eingeschränkten Berechtigungssatz ausgeführt werden, wird formuliert, dass sie mit teilweiser Vertrauenswürdigkeit ausgeführt werden.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Stellt eine Vielzahl von Support, um sicherzustellen, dass möglichst so viel Funktionalität sicher verwendet werden kann bei teilweiser Vertrauenswürdigkeit und zusammen mit [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)], bietet zusätzliche Unterstützung für die Programmierung mit teilweiser Vertrauenswürdigkeit.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [WPF-Funktionen für die Unterstützung von teilweiser Vertrauenswürdigkeit](#WPF_Feature_Partial_Trust_Support)  
  
-   [Programmieren für teilweise Vertrauenswürdigkeit](#Partial_Trust_Programming)  
  
-   [Verwalten von Berechtigungen](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## <a name="wpf-feature-partial-trust-support"></a>WPF-Funktionen für die Unterstützung von teilweiser Vertrauenswürdigkeit  
 Die folgende Tabelle enthält die allgemeinen Funktionen von Windows Presentation Foundation (WPF), die sicher innerhalb der Grenzen des Berechtigungssatzes für die Zone verwendet werden.  
  
 Tabelle 1: WPF-Funktionen, die bei teilweiser Vertrauenswürdigkeit sicher sind.  
  
|Bereich „Funktionen“|Feature|  
|------------------|-------------|  
|Allgemein|Browserfenster<br /><br /> Zugriff auf Ursprungswebsite<br /><br /> IsolatedStorage (beschränkt auf 512 KB)<br /><br /> UIAutomation-Anbieter<br /><br /> Befehle<br /><br /> Eingabemethoden-Editoren (Input Method Editors, IMEs)<br /><br /> Tablettstift und Freihandeingaben<br /><br /> Simuliertes Drag & Drop mit Ereignissen für Mausaufzeichnung und Bewegen<br /><br /> OpenFileDialog<br /><br /> XAML-Deserialisierung (über XamlReader.Load)|  
|Webintegration|Download-Dialogfeld des Browsers<br /><br /> Vom Benutzer initiierte Navigation auf oberster Ebene<br /><br /> mailto:links<br /><br /> Uniform Resource Identifier-Parameter<br /><br /> HTTPWebRequest<br /><br /> In einem IFRAME gehosteter WPF-Inhalt<br /><br /> Hosten von HTML-Seiten aus derselben Website mithilfe eines Frames<br /><br /> Hosten von HTML-Seiten aus derselben Website mithilfe von WebBrowser<br /><br /> Webdienste (ASMX)<br /><br /> Webdienste (über Windows Communication Foundation)<br /><br /> Skripterstellung<br /><br /> Dokumentobjektmodell|  
|Visuelle Objekte|2D und 3D<br /><br /> Animation<br /><br /> Medien (Ursprungswebsite und domänenübergreifend)<br /><br /> Imaging/Audio/Video|  
|Lesen|FlowDocuments<br /><br /> XPS-Dokumente<br /><br /> Eingebettete Schriftarten und Systemschriftarten<br /><br /> CFF- und TrueType-Schriftarten|  
|Bearbeiten|Rechtschreibprüfung<br /><br /> RichTextBox<br /><br /> Unterstützung der Zwischenablage bei Nur-Text und Freihand<br /><br /> Vom Benutzer initiiertes Einfügen<br /><br /> Kopieren von markiertem Inhalt|  
|Steuerelemente|Allgemeine Steuerelemente|  
  
 Diese Tabelle enthält die [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Funktionen auf hoher Ebene. Ausführlichere Informationen, die [!INCLUDE[TLA#tla_lhsdk](../../../includes/tlasharptla-lhsdk-md.md)] dokumentiert die Berechtigungen, die jedes Element im erforderlichen [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]. Zusätzlich gibt es für die folgenden Funktionen ausführlichere Informationen hinsichtlich des Ausführens bei teilweiser Vertrauenswürdigkeit, wozu auch spezielle Aspekte gehören.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] (finden Sie unter [XAML Overview (WPF)](./advanced/xaml-overview-wpf.md)).  
  
-   Popups (siehe <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>).  
  
-   Drag & Drop (finden Sie unter [Drag- and -Drop Overview](./advanced/drag-and-drop-overview.md)).  
  
-   Zwischenablage (finden Sie unter <xref:System.Windows.Clipboard?displayProperty=nameWithType>).  
  
-   Imaging (siehe <xref:System.Windows.Controls.Image?displayProperty=nameWithType>).  
  
-   Serialisierung (siehe <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>).  
  
-   Das Dialogfeld Datei öffnen (siehe <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>).  
  
 Der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] -Zone Features, die nicht sicher innerhalb der Grenzen des Internets ausgeführt werden.  
  
 Tabelle 2: WPF-Funktionen, die bei teilweiser Vertrauenswürdigkeit nicht sicher sind.  
  
|Bereich „Funktionen“|Feature|  
|------------------|-------------|  
|Allgemein|Fenster (anwendungsdefinierte Fenster und Dialogfelder)<br /><br /> SaveFileDialog<br /><br /> Dateisystem<br /><br /> Zugriff auf die Registrierung<br /><br /> Drag & Drop<br /><br /> XAML-Serialisierung (über XamlWriter.Save)<br /><br /> UIAutomation-Clients<br /><br /> Zugriff auf das Quellcodefenster (HwndHost)<br /><br /> Vollständige Sprachunterstützung<br /><br /> Windows Forms-Interoperabilität|  
|Visuelle Objekte|Bitmapeffekte<br /><br /> Bildcodierung|  
|Bearbeiten|Rich-Text-Format-Zwischenablage<br /><br /> Vollständige XAML-Unterstützung|  
  
<a name="Partial_Trust_Programming"></a>   
## <a name="partial-trust-programming"></a>Programmieren für teilweise Vertrauenswürdigkeit  
 Für [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] Anwendungen, Code, der den Standardberechtigungssatz hinausgeht verfügen über unterschiedliche Verhalten abhängig von der Sicherheitszone. In einigen Fällen erhält der Benutzer bei der Installation eine Warnung. Der Benutzer kann auswählen, ob die Installation fortgesetzt oder abgebrochen werden soll. In der folgenden Tabelle werden das Verhalten der Anwendung für jede Sicherheitszone und die erforderlichen Schritte für die volle Vertrauenswürdigkeit der Anwendung beschrieben.  
  
|Sicherheitszone|Verhalten|Erhalten der vollen Vertrauenswürdigkeit|  
|-------------------|--------------|------------------------|  
|Lokaler Computer|Automatisch volle Vertrauenswürdigkeit|Es ist keine Aktion erforderlich.|  
|Intranet und vertrauenswürdige Websites|Eingabeaufforderung für volle Vertrauenswürdigkeit|Signieren Sie die XBAP mit einem Zertifikat, damit der Benutzer die Quelle in der Eingabeaufforderung sieht.|  
|Internet|Schlägt fehl mit „Vertrauenswürdigkeit nicht gewährt“|Signieren Sie die XBAP mit einem Zertifikat.|  
  
> [!NOTE]
>  Das in der vorherigen Tabelle beschriebene Verhalten gilt für vollständig vertrauenswürdige XBAPs, die nicht dem ClickOnce-Modell für vertrauenswürdige Bereitstellung entsprechen.  
  
 Bei Code, der die zulässigen Berechtigungen überschreitet, handelt es sich normalerweise um gemeinsamen Code, der von eigenständigen und im Browser gehosteten Anwendungen gemeinsam verwendet wird. [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] und [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] bieten mehrere Verfahren für die Verwaltung dieses Szenarios.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### <a name="detecting-permissions-using-cas"></a>Erkennen von Berechtigungen mit CAS  
 In einigen Situationen ist es möglich, freigegebener Code in Bibliothekassemblys sowohl von eigenständigen Anwendungen unbefriedigend erwiesen und [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]. In diesen Fällen werden im Code möglicherweise Funktionen ausgeführt, die mehr Berechtigungen erfordern, als der Berechtigungssatz zulässt, der der Anwendung zugewiesen ist. Ihre Anwendung kann erkennen, ob sie eine bestimmte Berechtigung hat, mithilfe von Microsoft .NET Framework-Sicherheit. Insbesondere können sie prüfen, ob sie eine spezifische Berechtigung durch Aufrufen von hat das <xref:System.Security.CodeAccessPermission.Demand%2A> Methode für die Instanz der gewünschten Berechtigung. Dies wird im folgenden Beispiel gezeigt, das Code enthält, der überprüft, ob er eine Datei auf dem lokalen Datenträger speichern darf:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Wenn eine Anwendung keinen die gewünschte Berechtigung, den Aufruf von <xref:System.Security.CodeAccessPermission.Demand%2A> wird eine Sicherheitsausnahme ausgelöst. Andernfalls wurde die Berechtigung erteilt. `IsPermissionGranted` kapselt dieses Verhalten und gibt `true` oder `false` je nach Bedarf.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### <a name="graceful-degradation-of-functionality"></a>Sinnvolle Herabstufung der Funktionalität  
 Für Code, der aus verschiedenen Zonen ausgeführt werden, ist es sinnvoll, erkennen zu können, ob er die Berechtigung für seine auszuführenden Schritte hat. Während das Erkennen der Zone eine Geschichte ist, ist es weitaus besser, nach Möglichkeit eine Alternative für den Benutzer bereitzustellen. Beispielsweise ermöglicht eine Anwendung mit voller Vertrauenswürdigkeit Benutzern normalerweise, Dateien in beliebigen Speicherorten zu erstellen, während eine Anwendung mit teilweiser Vertrauenswürdigkeit Dateien nur in isoliertem Speicher erstellen kann. Wenn der Code zum Erstellen einer Datei in einer Assembly vorhanden ist, die sowohl von Anwendungen mit voller Vertrauenswürdigkeit (eigenständige Anwendungen) als auch von Anwendungen mit teilweiser Vertrauenswürdigkeit (im Browser gehostete Anwendungen) gemeinsam genutzt wird, und beide Anwendungen es Benutzern ermöglichen sollen, Dateien zu erstellen, muss der freigegebene Code erkennen, ob er mit voller oder teilweiser Vertrauenswürdigkeit ausgeführt wird, bevor eine Datei am entsprechenden Speicherort erstellt wird. Im folgenden Code werden beide Fälle veranschaulicht.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 In vielen Fällen sollte es Ihnen möglich sein, eine Alternative zu teilweiser Vertrauenswürdigkeit zu finden.  
  
 In einer kontrollierten Umgebung, beispielsweise einem Intranet, können benutzerdefinierte verwaltete Frameworks über die Clientbasis installiert werden die [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)]. Diese Bibliotheken können Code, der volle Vertrauenswürdigkeit erfordert "ausführen", und von Anwendungen, die teilweise Vertrauenswürdigkeit mit nur zulässig sind, verwiesen werden <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (Weitere Informationen finden Sie unter [Sicherheit](security-wpf.md) und [WPF-Sicherheit Strategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)).  
  
<a name="Browser_Host_Detection"></a>   
### <a name="browser-host-detection"></a>Browserhosterkennung  
 Mithilfe von [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] zum Überprüfen von Berechtigungen ist ein geeignetes Verfahren, wenn Sie eine Berechtigungsbasis prüfen müssen. Allerdings ist für dieses Verfahren das Abfangen von Ausnahmen als Teil der normalen Verarbeitung erforderlich, was grundsätzlich nicht empfehlenswert ist und Leistungsprobleme verursachen kann. Stattdessen, wenn Ihre [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] in den Sicherheitssandkasten der Internetzone wird nur ausgeführt, können Sie die <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> -Eigenschaft, die für "true" zurückgibt [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
> [!NOTE]
>  <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A> nur unterscheidet, ob eine Anwendung in einem Browser ausgeführt wird, nicht die Gruppe von Berechtigungen einer Anwendung mit ausgeführt wird.  
  
<a name="Managing_Permissions"></a>   
## <a name="managing-permissions"></a>Verwalten von Berechtigungen  
 In der Standardeinstellung [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] mit teilweiser Vertrauenswürdigkeit (Standardberechtigungssatz für die Zone) ausgeführt. Je nach Anforderungen der Anwendung ist es jedoch möglich, den Standardberechtigungssatz durch einen anderen Berechtigungssatz zu ersetzen. Z. B. wenn ein [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] gestartet wird aus einem lokalen Intranet, sie nutzen ein erweiterter Berechtigungssatz, der in der folgenden Tabelle angezeigt wird.  
  
 Tabelle 3: LocalIntranet- und Internetberechtigungen  
  
|Berechtigung|Attribut|LocalIntranet|Internet|  
|----------------|---------------|-------------------|--------------|  
|DNS|Zugriff auf DNS-Server|Ja|Nein|  
|Umgebungsvariablen|Thema|Ja|Nein|  
|Dateidialogfelder|Öffnen|Ja|Ja|  
|Dateidialogfelder|Uneingeschränkt|Ja|Nein|  
|Isolierte Speicherung|Assemblyisolation durch Benutzer|Ja|Nein|  
|Isolierte Speicherung|Unbekannte isolation|Ja|Ja|  
|Isolierte Speicherung|Unbegrenztes Benutzerkontingent|Ja|Nein|  
|Medien|Sicherheit für Audio, Video und Bilder|Ja|Ja|  
|Drucken|Standarddruck|Ja|Nein|  
|Drucken|Sicheres Drucken|Ja|Ja|  
|Spiegelung|Ausgabe|Ja|Nein|  
|Sicherheit|Ausführen von verwaltetem Code|Ja|Ja|  
|Sicherheit|Bestätigen von erteilten Berechtigungen|Ja|Nein|  
|Benutzeroberfläche|Uneingeschränkt|Ja|Nein|  
|Benutzeroberfläche|Sichere Fenster der obersten Ebene|Ja|Ja|  
|Benutzeroberfläche|Eigene Zwischenablage|Ja|Ja|  
|Webbrowser|Sichere Frame-Navigation zu HTML|Ja|Ja|  
  
> [!NOTE]
>  Ausschneiden und Einfügen ist bei teilweiser Vertrauenswürdigkeit nur bei Ausführen durch den Benutzer zulässig.  
  
 Müssen Sie Berechtigungen erhöhen, müssen Sie die Projekteinstellungen und das ClickOnce-Anwendungsmanifest ändern. Weitere Informationen finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](./app-development/wpf-xaml-browser-applications-overview.md). Möglicherweise sind auch die folgenden Dokumente hilfreich.  
  
-   [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](../tools/mage-exe-manifest-generation-and-editing-tool.md)  
  
-   [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
  
-   [Sichern von ClickOnce-Anwendungen](/visualstudio/deployment/securing-clickonce-applications)  
  
 Wenn Ihre [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] volle Vertrauenswürdigkeit erfordert, Sie können den gleichen Tools verwenden, um die erforderlichen Berechtigungen zu erhöhen. Obwohl eine [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] erhalten nur volle Vertrauenswürdigkeit, wenn er installiert ist und aus dem lokalen Computer und dem Intranet oder über eine URL, die in des Browsers aufgelistet ist, vertrauenswürdigen oder zugelassenen Websites gestartet werden. Wird die Anwendung aus dem Intranet oder einer vertrauenswürdigen Website installiert, wird der Benutzer durch die Standard-ClickOnce-Eingabeaufforderung über die erhöhten Berechtigungen informiert. Der Benutzer kann auswählen, ob die Installation fortgesetzt oder abgebrochen werden soll.  
  
 Alternativ können Sie das ClickOnce-Modell für vertrauenswürdige Bereitstellung für eine Bereitstellung mit voller Vertrauenswürdigkeit aus einer beliebigen Sicherheitszone verwenden. Weitere Informationen finden Sie unter [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview) und [Sicherheit](security-wpf.md).  
  
## <a name="see-also"></a>Siehe auch
- [Sicherheit](security-wpf.md)
- [WPF-Sicherheitsstrategie – Plattformsicherheit](wpf-security-strategy-platform-security.md)
- [WPF-Sicherheitsstrategie – Sicherheitsentwicklung](wpf-security-strategy-security-engineering.md)
