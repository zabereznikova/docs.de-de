---
title: "WPF-Sicherheit mit teilweiser Vertrauensw&#252;rdigkeit | Microsoft Docs"
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
  - "Debuggen von teilweise vertrauenswürdigen Anwendungen"
  - "Erkennen von Berechtigungen"
  - "Funktionssicherheitsanforderungen"
  - "Verwalten von Berechtigungen"
  - "Teilweise vertrauenswürdige Anwendungen, Debuggen"
  - "Sicherheit mit teilweiser Vertrauenswürdigkeit"
  - "-Berechtigungen, Ermitteln"
  - "-Berechtigungen, Verwalten"
  - "Sicherheitseinstellungen für Internet Explorer"
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
caps.latest.revision: 40
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# WPF-Sicherheit mit teilweiser Vertrauensw&#252;rdigkeit
<a name="introduction"></a> Im Allgemeinen sollte der direkte Zugriff von Internetanwendungen auf wichtige Systemressourcen beschränkt werden, um böswillige Beschädigungen zu vermeiden.  Standardmäßig können [!INCLUDE[TLA#tla_html](../../../includes/tlasharptla-html-md.md)] und clientseitige Skriptsprachen nicht auf wichtige Systemressourcen zugreifen.  Da im Browser gehostete [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen vom Browser aus gestartet werden können, sollten für sie ähnliche Beschränkungen gelten.  Um diese Beschränkungen durchzusetzen, verwendet [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] sowohl [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] als auch [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] \(siehe [WPF\-Sicherheitsstrategie – Plattformsicherheit](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)\).  Standardmäßig fordern im Browser gehostete Anwendungen den [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]\-Berechtigungssatz für die Internetzone an. Dies geschieht unabhängig davon, ob diese Anwendungen vom Internet, dem lokalen Intranet oder dem lokalen Computer aus gestartet werden.  Anwendungen, die nicht mit einem Berechtigungssatz ausgeführt werden, der nicht dem vollen Berechtigungssatz entspricht, werden mit teilweiser Vertrauenswürdigkeit ausgeführt.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] bietet viele Arten der Unterstützung, um sicherzustellen, dass bei teilweiser Vertrauenswürdigkeit möglichst viele Funktionen sicher ausgeführt werden können, und bietet zusammen mit [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] zusätzliche Unterstützung für die Programmierung mit teilweiser Vertrauenswürdigkeit.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [WPF\-Features für die Unterstützung von teilweiser Vertrauenswürdigkeit](#WPF_Feature_Partial_Trust_Support)  
  
-   [Programmierung mit teilweiser Vertrauenswürdigkeit](#Partial_Trust_Programming)  
  
-   [Verwalten von Berechtigungen](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## WPF\-Features für die Unterstützung von teilweiser Vertrauenswürdigkeit  
 Die folgende Tabelle enthält die wichtigsten Funktionen von [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)], die unbedenklich im Rahmen des Berechtigungssatzes für die Internetzone verwendet werden können.  
  
 Tabelle 1: Sichere WPF\-Features bei teilweiser Vertrauenswürdigkeit  
  
|Funktionsbereich|Feature|  
|----------------------|-------------|  
|Allgemein|Browserfenster<br /><br /> Zugriff auf die Ursprungssite<br /><br /> IsolatedStorage \(beschränkt auf 512 KB\)<br /><br /> UIAutomation\-Anbieter<br /><br /> Befehle<br /><br /> Eingabemethoden\-Editoren \(IMEs\)<br /><br /> Tablettstift und Freihandeingabe<br /><br /> Simuliertes Drag & Drop mit Ereignissen zur Mausaufzeichnung und zum Verschieben<br /><br /> OpenFileDialog<br /><br /> XAML\-Deserialisierung \(über XamlReader.Load\)|  
|Webintegration|Download\-Dialogfeld des Browsers<br /><br /> Vom Benutzer initiierte Navigation der obersten Ebene<br /><br /> mailto:links<br /><br /> Uniform Resource Identifier\-Parameter<br /><br /> HTTPWebRequest<br /><br /> In einem IFRAME gehosteter WPF\-Inhalt<br /><br /> Hosten von HTML\-Seiten mithilfe eines Frames<br /><br /> Hosten von HTML\-Seiten mithilfe eines Webbrowsers<br /><br /> Webdienste \(ASMX\)<br /><br /> Webdienste \(Verwendung von Windows Communication Foundation\)<br /><br /> Skripterstellung<br /><br /> Dokumentobjektmodell|  
|Darstellung|2D und 3D<br /><br /> Animation<br /><br /> Medien \(Ursprungssite und domänenübergreifend\)<br /><br /> Imaging\/Audio\/Video|  
|Lesen|FlowDocuments<br /><br /> XPS\-Dokumente<br /><br /> Eingebettete Schriftarten & Systemschriftarten<br /><br /> CFF\- & TrueType\-Schriftarten|  
|Bearbeiten|Rechtschreibprüfung<br /><br /> RichTextBox<br /><br /> Unterstützung der Zwischenablage bei Nur\-Text und Freihand<br /><br /> Vom Benutzer initiiertes Einfügen<br /><br /> Kopieren von ausgewähltem Inhalt|  
|Steuerelemente|Allgemeine Steuerelemente|  
  
 Diese Tabelle enthält die wichtigsten [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Features.  Ausführlichere Informationen finden Sie in [!INCLUDE[TLA#tla_lhsdk](../../../includes/tlasharptla-lhsdk-md.md)]. Hier werden die für jedes Member in [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] erforderlichen Berechtigungen dokumentiert.  Darüber hinaus weisen die folgenden Funktionen ausführlichere Informationen hinsichtlich der Ausführung unter teilweiser Vertrauenswürdigkeit auf, einschließlich besonderer Überlegungen.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] \(siehe [Übersicht über XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)\).  
  
-   Popups \(siehe <xref:System.Windows.Controls.Primitives.Popup?displayProperty=fullName>\).  
  
-   Drag & Drop \(siehe [Übersicht über Drag & Drop](../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)\).  
  
-   Zwischenablage \(siehe <xref:System.Windows.Clipboard?displayProperty=fullName>\).  
  
-   Imaging \(siehe <xref:System.Windows.Controls.Image?displayProperty=fullName>\).  
  
-   Serialisierung \(siehe <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=fullName>\).  
  
-   Dialogfeld Datei öffnen \(siehe <xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName>\).  
  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Funktionen, die im Rahmen des Berechtigungssatzes für die Internetzone nicht unbedenklich verwendet werden können.  
  
 Tabelle 2: WPF\-Features, die bei teilweiser Vertrauenswürdigkeit nicht sicher sind  
  
|Funktionsbereich|Feature|  
|----------------------|-------------|  
|Allgemein|Fenster \(anwendungsdefinierte Fenster und Dialogfelder\)<br /><br /> SaveFileDialog<br /><br /> Dateisystem<br /><br /> Registrierungszugriff<br /><br /> Drag & Drop<br /><br /> XAML\-Serialisierung \(über XamlWriter.Save\)<br /><br /> UIAutomation\-Clients<br /><br /> Zugriff auf das Quellcodefenster \(HwndHost\)<br /><br /> Vollständige Sprachunterstützung<br /><br /> Windows Forms\-Interoperabilität|  
|Darstellung|Bitmapeffekte<br /><br /> Bildcodierung|  
|Bearbeiten|Rich Text Format\-Zwischenablage<br /><br /> Vollständige XAML\-Unterstützung|  
  
<a name="Partial_Trust_Programming"></a>   
## Programmierung mit teilweiser Vertrauenswürdigkeit  
 Bei [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)]\-Anwendungen weist Code, der über den Standardberechtigungssatz hinausgeht, abhängig von der Sicherheitszone ein anderes Verhalten auf.  In einigen Fällen erhält der Benutzer bei der Installation eine Warnung.  Der Benutzer kann auswählen, ob die Installation fortgesetzt oder abgebrochen werden soll.  In der folgenden Tabelle werden das Verhalten der Anwendung für jede Sicherheitszone und die erforderlichen Schritte für die volle Vertrauenswürdigkeit der Anwendung beschrieben.  
  
|Sicherheitszone|Verhalten|Erhalten der vollen Vertrauenswürdigkeit|  
|---------------------|---------------|----------------------------------------------|  
|Lokaler Computer|Automatische volle Vertrauenswürdigkeit|Es ist keine Aktion erforderlich.|  
|Intranet und vertrauenswürdige Sites|Eingabeaufforderung für volle Vertrauenswürdigkeit|Signieren Sie die XBAP mit einem Zertifikat, damit der Benutzer die Quelle in der Eingabeaufforderung sieht.|  
|Internet|Schlägt fehl mit "Vertrauenswürdigkeit nicht gewährt"|Signieren Sie die XBAP mit einem Zertifikat.|  
  
> [!NOTE]
>  Das in der vorherigen Tabelle beschriebene Verhalten gilt für vollständig vertrauenswürdige XBAPs, die nicht dem ClickOnce Trusted Bereitstellungsmodell folgen.  
  
 Bei Code, der die zulässigen Berechtigungen überschreitet, handelt es sich normalerweise um gemeinsamen Code, der von eigenständigen und im Browser gehosteten Anwendungen gemeinsam verwendet wird.  [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] und [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] bieten mehrere Verfahren für die Verwaltung dieses Szenarios.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### Erkennen von Berechtigungen mithilfe der Codezugriffssicherheit \(CAS\)  
 In manchen Situationen kann freigegebener Code in Bibliothekassemblys sowohl von eigenständigen Anwendungen als auch von [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] verwendet werden.  In diesen Fällen werden vom Code möglicherweise Funktionen ausgeführt, für die Berechtigungen erforderlich sind, die über den der Anwendung zugewiesenen Berechtigungssatz hinausgehen.  Mithilfe der [!INCLUDE[TLA#tla_winfx](../../../includes/tlasharptla-winfx-md.md)]\-Sicherheit kann die Anwendung erkennen, ob sie über eine bestimmte Berechtigung verfügt.  Insbesondere kann sie prüfen, ob sie über eine bestimmte Berechtigung verfügt, indem sie die <xref:System.Security.CodeAccessPermission.Demand%2A>\-Methode auf der Instanz der gewünschten Berechtigung aufruft.  Dies wird im folgenden Beispiel gezeigt. Dieses Beispiel enthält Code, der überprüft, ob er die Fähigkeit besitzt, eine Datei auf dem lokalen Datenträger zu speichern:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Wenn eine Anwendung die gewünschte Berechtigung nicht besitzt, löst der Aufruf von <xref:System.Security.CodeAccessPermission.Demand%2A> eine Sicherheitsausnahme aus.  Andernfalls wurde die Berechtigung gewährt.  `IsPermissionGranted` kapselt dieses Verhalten und gibt jeweils `true` oder `false` zurück.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### Ordnungsgemäße Verringerung der Funktionalität  
 Die Fähigkeit, festzustellen, ob Code die Berechtigung besitzt, nötige Funktionen auszuführen, ist für Code interessant, der von verschiedenen Zonen aus ausgeführt werden kann.  Das Erkennen der Zone ist zwar eine wichtige Funktion, jedoch ist es generell vorzuziehen, wenn möglich eine Alternative für den Benutzer bereitzustellen.  So ermöglicht eine Anwendung mit voller Vertrauenswürdigkeit Benutzern normalerweise, an jeder beliebigen Stelle Dateien zu erstellen, während eine Anwendung mit teilweiser Vertrauenswürdigkeit nur in der isolierten Speicherung Dateien erstellen kann.  Wenn der Code zum Erstellen einer Datei in einer Assembly vorhanden ist, die sowohl von Anwendungen mit voller Vertrauenswürdigkeit \(eigenständige Anwendungen\) als auch von Anwendungen mit teilweiser Vertrauenswürdigkeit \(im Browser gehostete Anwendungen\) gemeinsam genutzt wird, und beide Anwendungen es Benutzern ermöglichen sollen, Dateien zu erstellen, sollte der freigegebene Code feststellen, ob er mit voller oder teilweiser Vertrauenswürdigkeit ausgeführt wird, bevor eine Datei am entsprechenden Speicherort erstellt wird.  Im folgenden Code werden beide Fälle veranschaulicht.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 In vielen Fällen sollte es Ihnen möglich sein, eine Alternative mit teilweiser Vertrauenswürdigkeit zu finden.  
  
 In einer kontrollierten Umgebung, wie beispielsweise einem Intranet, können benutzerdefinierte verwaltete Frameworks über die Client\-Basis in den [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)] installiert werden.  Diese Bibliotheken können Code ausführen, der volle Vertrauenswürdigkeit erfordert, und auf sie kann von Anwendungen mit teilweiser Vertrauenswürdigkeit aus mithilfe von <xref:System.Security.AllowPartiallyTrustedCallersAttribute> verwiesen werden \(weitere Informationen finden Sie unter [Sicherheit](../../../docs/framework/wpf/security-wpf.md) und [WPF\-Sicherheitsstrategie – Plattformsicherheit](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)\).  
  
<a name="Browser_Host_Detection"></a>   
### Browserhosterkennung  
 Das Verwenden von [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] zum Überprüfen von Berechtigungen ist ein geeignetes Verfahren, wenn Sie auf Berechtigungsbasis überprüfen müssen.  Dieses Verfahren hängt jedoch davon ab, ob Ausnahmen als Teil der normalen Verarbeitung abgefangen werden, was im Allgemeinen nicht empfehlenswert ist und sich auf die Leistung auswirken kann.  Wenn Ihre [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] nur in der Sandbox der Internetzone ausgeführt wird, können Sie die <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=fullName>\-Eigenschaft verwenden, die für [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] "true" zurückgibt.  
  
> [!NOTE]
>  <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A> erkennt nur, ob eine Anwendung in einem Browser ausgeführt wird. Es wird nicht erkannt, mit welchem Berechtigungssatz eine Anwendung ausgeführt wird.  
  
<a name="Managing_Permissions"></a>   
## Verwalten von Berechtigungen  
 Standardmäßig werden [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] mit teilweiser Vertrauenswürdigkeit \(Standardberechtigungssatz für die Internetzone\) ausgeführt.  Je nach den Anforderungen der Anwendung ist es jedoch möglich, den Berechtigungssatz zu ändern.  Wenn beispielsweise [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] von einem lokalen Intranet aus gestartet werden, können sie von einem erweiterten Berechtigungssatz profitieren, wie in der folgenden Tabelle gezeigt wird.  
  
 Tabelle 3: LocalIntranet und Internetberechtigungen  
  
|Berechtigung|Attribut|LocalIntranet|Internet|  
|------------------|--------------|-------------------|--------------|  
|DNS|Zugriff DNS\-Server|Ja|Nein|  
|Umgebungsvariablen|Thema|Ja|Nein|  
|Dateidialogfelder|Öffnen Sie .|Ja|Ja|  
|Dateidialogfelder|Uneingeschränkt|Ja|Nein|  
|Isolierte Speicherung|Assemblyisolation nach Benutzer|Ja|Nein|  
|Isolierte Speicherung|Unbekannte Isolation|Ja|Ja|  
|Isolierte Speicherung|Unbegrenztes Benutzerkontingent|Ja|Nein|  
|Medien|Sicherheit für Audio, Video und Bilder|Ja|Ja|  
|Drucken|Standarddruck|Ja|Nein|  
|Drucken|Sicheres Drucken|Ja|Ja|  
|Reflektion|Ausgabe|Ja|Nein|  
|Sicherheit|Ausführen von verwaltetem Code|Ja|Ja|  
|Sicherheit|Bestätigen von gewährten Berechtigungen|Ja|Nein|  
|Benutzeroberfläche|Uneingeschränkt|Ja|Nein|  
|Benutzeroberfläche|Sichere Fenster der obersten Ebene|Ja|Ja|  
|Benutzeroberfläche|Eigene Zwischenablage|Ja|Ja|  
|Webbrowser|Sichere Frame\-Navigation zu HTML|Ja|Ja|  
  
> [!NOTE]
>  Ausschneiden und Einfügen ist nur bei Initialisierung durch den Benutzer unter teilweiser Vertrauenswürdigkeit zulässig.  
  
 Wenn Sie Berechtigungen erweitern müssen, müssen Sie die Projekteinstellungen und das ClickOnce\-Anwendungsmanifest ändern.  Weitere Informationen finden Sie unter [Übersicht über WPF\-XAML\-Browseranwendungen](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  Möglicherweise sind auch die folgenden Dokumente hilfreich.  
  
-   [Mage.exe \(Tool zum Generieren und Bearbeiten von Manifesten\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
-   [MageUI.exe \(Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client\)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
-   [Sichern von ClickOnce\-Anwendungen](../Topic/Securing%20ClickOnce%20Applications.md).  
  
 Wenn die [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] volle Vertrauenswürdigkeit erfordert, können Sie die gleichen Tools verwenden, um die erforderlichen Berechtigungen zu erweitern.  Allerdings erhält eine [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] nur dann volle Vertrauenswürdigkeit, wenn sie auf dem lokalen Computer installiert und von diesem Computer, dem Intranet oder einer URL, die als vertrauenswürdige oder zugelassene Website aufgelistet ist, gestartet wird.  Wenn die Anwendung vom Intranet oder einer vertrauenswürdigen Website installiert ist, wird der Benutzer durch die Standard\-ClickOnce\-Eingabeaufforderung über die erhöhten Berechtigungen informiert.  Der Benutzer kann auswählen, ob die Installation fortgesetzt oder abgebrochen werden soll.  
  
 Alternativ können Sie das vertrauenswürdige ClickOnce\-Bereitstellungsmodell für die voll vertrauenswürdige Bereitstellung aus einer beliebigen Sicherheitszone verwenden.  Weitere Informationen finden Sie unter [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](../Topic/Trusted%20Application%20Deployment%20Overview.md) und [Sicherheit](../../../docs/framework/wpf/security-wpf.md).  
  
## Siehe auch  
 [Sicherheit](../../../docs/framework/wpf/security-wpf.md)   
 [WPF\-Sicherheitsstrategie – Plattformsicherheit](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [WPF\-Sicherheitsstrategie – Sicherheitsentwicklung](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)