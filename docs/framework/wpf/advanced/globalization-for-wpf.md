---
title: "Globalisierung f&#252;r WPF | Microsoft Docs"
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
  - "Globalisierung"
  - "Internationale Benutzeroberfläche, XAML"
  - "XAML, Globalisierung"
  - "XAML, Internationale Benutzeroberfläche"
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Globalisierung f&#252;r WPF
In diesem Thema werden Aspekte beschrieben, die Sie beim Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen für den weltweiten Markt beachten sollten.  Die Programmierelemente für die Globalisierung werden in [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization` definiert.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="xaml_globalization"></a>   
## XAML\-Globalisierung  
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] basiert auf [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] und nutzt die in der [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Spezifikation definierte Globalisierungsunterstützung.  In den folgenden Abschnitten werden einige wichtige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Features beschrieben, die Sie beachten sollten.  
  
<a name="char_reference"></a>   
### Zeichenverweise  
 Ein Zeichenverweis gibt die Nummer für das jeweilige [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]\-Zeichen im Dezimal\- oder Hexadezimalformat an.  Im folgenden Beispiel wird ein Dezimalzeichenverweis veranschaulicht.  
  
```  
Ϩ  
```  
  
 In diesem Beispiel wird ein Hexadezimalzeichenverweis veranschaulicht.  Beachten Sie, dass vor der Hexadezimalzahl ein **x** steht.  
  
```  
Ϩ  
```  
  
<a name="encoding"></a>   
### Codierung  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützt die Codierungen [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF\-16 und UTF\-8.  Die Codierungsanweisung steht am Anfang des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dokuments.  Wenn kein Codierungsattribut vorhanden ist und keine Bytereihenfolge festgelegt ist, verwendet der Parser standardmäßig UTF\-8.  UTF\-8 und UTF\-16 sind die bevorzugten Codierungen.  UTF\-7 wird nicht unterstützt.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine UTF\-8\-Codierung in einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei angeben.  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### Language\-Attribut  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md), um das Sprachattribut eines Elements darzustellen.  Um die <xref:System.Globalization.CultureInfo>\-Klasse zu nutzen, muss als Sprachattributwert einer der von <xref:System.Globalization.CultureInfo> vordefinierten Kulturnamen verwendet werden.  [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) ist in der Elementstruktur vererbbar \(durch XML\-Regeln, nicht unbedingt wegen der Vererbung einer Abhängigkeitseigenschaft\). Der Standardwert ist eine leere Zeichenfolge, sofern keine explizite Zuweisung vorhanden ist.  
  
 Das Sprachattribut ist sehr nützlich für die Angabe von Dialekten.  Zum Beispiel hat Französisch eine andere Rechtschreibung, ein anderes Vokabular und eine andere Aussprache in Frankreich, Quebec, Belgien und der Schweiz.  Auch Chinesisch, Japanisch und Koreanisch nutzen Codepunkte in [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] gemeinsam, während sich die ideografischen Formen unterscheiden und völlig andere Schriftarten verwendet werden.  
  
 Im folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispiel wird das `fr-CA`\-Sprachattribut verwendet, um kanadisches Französisch anzugeben.  
  
```  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützt alle [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]\-Features einschließlich der Ersatzzeichen.  Solange der Zeichensatz [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] zugeordnet werden kann, wird er unterstützt.  GB18030 führt beispielsweise einige Zeichen ein, die der Chinesisch, Japanisch und Koreanisch \(CFK\)\-Erweiterung A and B sowie Ersatzzeichenpaaren zugeordnet werden. Daher wird dieser Zeichensatz voll unterstützt.  Eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung kann mit <xref:System.Globalization.StringInfo> Zeichenfolgen bearbeiten, ohne zu wissen, ob es dafür Ersatzzeichenpaare oder Kombinationszeichen gibt.  
  
<a name="design_intl_ui_with_xaml"></a>   
## Entwerfen einer internationalen Benutzeroberfläche mit XAML  
 In diesem Abschnitt werden Features der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] beschrieben, die Sie beim Schreiben einer Anwendung beachten sollten.  
  
<a name="intl_text"></a>   
### Internationaler Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] beinhaltet die integrierte Verarbeitung aller Schreibsysteme, die [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] unterstützt.  
  
 Zurzeit werden die folgenden Skripts unterstützt:  
  
-   Arabisch  
  
-   Bangla  
  
-   Devanagari  
  
-   Kyrillisch  
  
-   Griechisch  
  
-   Gujarati  
  
-   Gurmukhi  
  
-   Hebräisch  
  
-   Ideografische Skripts  
  
-   Kannada  
  
-   Laotisch  
  
-   Lateinisch  
  
-   Malayalam  
  
-   Mongolisch  
  
-   Odia  
  
-   Syrisch  
  
-   Tamil  
  
-   Telugu  
  
-   Thaana  
  
-   Thailändisch\*  
  
-   Tibetanisch  
  
 \*In dieser Version werden die Anzeige und Bearbeitung, nicht jedoch die Worttrennung in thailändischem Text unterstützt.  
  
 Die folgenden Skripts werden zurzeit nicht unterstützt:  
  
-   Khmer  
  
-   Koreanisch \(Hangul\)  
  
-   Myanmar  
  
-   Sinhala  
  
 Alle Schreibsystemmodule unterstützen [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]\-Schriften.  [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriften können die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Layouttabellen enthalten. Sie erleichtern den Entwicklern das Entwerfen internationaler und hochwertiger typografischer Schriften.  Die Layouttabellen für [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriften enthalten Informationen über Symbolersetzungen, die Symbolpositionierung, die Ausrichtung und die Baselinepositionierung. Mit ihrer Hilfe können Textverarbeitungsanwendungen das Textlayout optimieren.  
  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriften ermöglichen die Verwaltung großer Symbolsätze mithilfe der [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]\-Codierung.  Diese Codierung gewährleistet eine breite internationale Unterstützung sowie typografische Symbolvarianten.  
  
 Für das Textrendering nutzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Subpixel\-Technologie von [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]. Diese Technologie unterstützt die Auflösungsunabhängigkeit.  Sie verbessert die Lesbarkeit enorm und ermöglicht Dokumenten für alle Skripts eine Qualität wie bei hochwertigen Magazinen.  
  
<a name="intl_layout"></a>   
### Internationales Layout  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine sehr komfortable Möglichkeit der Unterstützung horizontaler, bidirektionaler und vertikaler Layouts.  In PresentationFramework kann die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft zur Definition des Layouts verwendet werden.  Folgende Flussrichtungsmuster stehen zur Verfügung:  
  
-   *LeftToRight* \- horizontales Layout für Lateinisch, ostasiatische Sprachen usw.  
  
-   *RightToLeft* \- bidirektional für Arabisch, Hebräisch usw.  
  
<a name="developing_localizable_apps"></a>   
## Entwickeln von lokalisierbaren Anwendungen  
 Wenn Sie eine Anwendung für die weltweite Nutzung schreiben, müssen Sie auf die Lokalisierbarkeit der Anwendung achten.  In den folgenden Themen werden relevante Punkte in diesem Zusammenhang erörtert.  
  
<a name="mui"></a>   
### Mehrsprachige Benutzeroberfläche  
 Durch die mehrsprachigen Benutzeroberflächen \(MUI, Multilanguage User Interface\) unterstützt [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] das Umschalten von einer Sprache zu einer anderen in den [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  Eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung verwendet das Assemblymodell zur Unterstützung von MUI.  Eine Anwendung enthält sprachneutrale Assemblys sowie sprachabhängige Satellitenressourcenassemblys.  Der Einstiegspunkt ist eine verwaltete EXE\-Datei in der Hauptassembly.  Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ressourcenladeprogramm nutzt den Ressourcenmanager von [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)], um die Ressourcensuche und das Fallback zu unterstützen.  Mehrere Sprachsatellitenassemblys arbeiten mit derselben Hauptassembly.  Die geladene Ressourcenassembly hängt von der <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> des aktuellen Threads ab.  
  
<a name="localizable_ui"></a>   
### Lokalisierbare Benutzeroberfläche  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen definieren ihre [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] können Entwickler eine Hierarchie von Objekten mit einem Satz von Eigenschaften und Logik angeben.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird hauptsächlich verwendet, um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen zu entwickeln. Sie können damit aber auch eine Hierarchie beliebiger [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekte angeben.  Die meisten Entwickler gestalten mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ihrer Anwendung und verwenden eine Programmiersprache wie [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] für Reaktionen auf Benutzerinteraktion.  
  
 Aus Ressourcensicht ist eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei, die eine sprachabhängige [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] beschreiben soll, ein Ressourcenelement. Daher muss ihr endgültiges Verteilungsformat lokalisierbar sein, um internationale Sprachen zu unterstützen.  Da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] keine Ereignisse verwalten kann, enthalten viele [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Anwendungen zu diesem Zweck Codeblöcke.  Weitere Informationen finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  Code wird entfernt und in verschiedenen Binärdateien kompiliert, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei mit Tokens in die BAML\-Form von XAML zerlegt wird. Die BAML\-Form von XAML\-Dateien, Bilder und andere Arten verwalteter Ressourcenobjekte werden entweder in die Satellitenressourcenassembly eingebettet, die in andere Sprachen lokalisiert werden kann, oder in die Hauptassembly, wenn keine Lokalisierung erforderlich ist.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen unterstützen alle [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]\-[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ressourcen einschließlich Zeichenfolgentabellen, Bilder usw.  
  
<a name="building_localizable_apps"></a>   
### Erstellen von lokalisierbaren Anwendungen  
 Lokalisierung bedeutet, eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für andere Länder anzupassen.  Wenn eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung lokalisierbar sein soll, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen.  Die Ressourcenassembly wird in verschiedene Sprachen lokalisiert, und der Code\-Behind wird mithilfe der Ressourcenverwaltungs\-[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] geladen.  Eine der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung ist eine Projektdatei \(.proj\).  Alle in der Anwendung verwendeten Ressourcen müssen in der Projektdatei enthalten sein.  Im folgenden Beispiel aus einer CSPROJ\-Datei wird veranschaulicht, wie Sie dafür vorgehen müssen.  
  
```  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 Um eine Ressource in der Anwendung zu verwenden, instanziieren Sie <xref:System.Resources.ResourceManager>, und laden Sie die zu verwendende Ressource.  Im folgenden Beispiel wird veranschaulicht, wie Sie dafür vorgehen müssen.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## Verwenden von ClickOnce in lokalisierten Anwendungen  
 ClickOnce ist eine neue Windows Forms\-Bereitstellungstechnologie, die im Lieferumfang von [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] enthalten ist.  Es ermöglicht die Anwendungsinstallation und Aktualisierung von Webanwendungen.  Wenn eine mit ClickOnce bereitgestellte Anwendung lokalisiert ist, kann sie nur in der lokalisierten Kultur angezeigt werden.  Beispiel: Wenn eine bereitgestellte Anwendung in Japanisch lokalisiert ist, kann sie nur unter dem japanischen [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] und nicht unter dem englischen [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] angezeigt werden.  Dies ist ein Problem, weil japanische Benutzer häufig auch eine englische Version von [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] ausführen.  
  
 Dieses Problem wird durch die Einstellung des neutralen Sprachfallbackattributs gelöst.  Ein Anwendungsentwickler kann optional Ressourcen aus der Hauptassembly entfernen und angeben, dass sich die Ressourcen in einer Satellitenassembly für eine spezifische Kultur befinden.  Zur Steuerung dieses Prozesses verwenden Sie <xref:System.Resources.NeutralResourcesLanguageAttribute>.  Der Konstruktor der <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Klasse hat zwei Signaturen. Eine Signatur verwendet einen <xref:System.Resources.UltimateResourceFallbackLocation>\-Parameter, um die Position anzugeben, an der <xref:System.Resources.ResourceManager> die Fallbackressourcen extrahieren soll: die Hauptassembly oder eine Satellitenassembly.  Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden.  Für die endgültige Fallbackposition weist der Code <xref:System.Resources.ResourceManager> an, im Verzeichnis der aktuell ausgeführten Assembly im Unterverzeichnis "de" nach den Ressourcen zu suchen.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
  
```  
  
## Siehe auch  
 [Übersicht über WPF\-Globalisierung und \-Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)