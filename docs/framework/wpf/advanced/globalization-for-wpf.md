---
title: "Globalisierung für WPF"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 418a1b6d2033b8bc84a18578cfc227c5f227ad91
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="globalization-for-wpf"></a>Globalisierung für WPF
Dieses Thema enthält Probleme, die Sie beim Schreiben von kennen sollten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen für den globalen Markt. Die Globalisierung Programmierelemente in definiert werden [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization`.  
  

  
<a name="xaml_globalization"></a>   
## <a name="xaml-globalization"></a>XAML-Globalisierung  
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)]basiert auf [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] und nutzt die Globalisierung-Unterstützung in definiert die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Spezifikation. Den folgenden Abschnitten werden einige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Funktionen, die Sie kennen sollten.  
  
<a name="char_reference"></a>   
### <a name="character-references"></a>Zeichenverweise  
Ein Zeichenverweis gibt UTF16-Codeeinheit des entsprechenden [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] es darstellt, die im dezimalen oder hexadezimalen Zeichen. Das folgende Beispiel zeigt einen dezimalen Zeichenverweis für KOPTISCH GROßBUCHSTABE h oder "Ϩ":

```
&#1000;
```

Das folgende Beispiel zeigt einen Verweis hexadezimalen Zeichen. Beachten Sie, die eine **x** vor hexadezimale Zahl.

```
&#x3E8;
```

<a name="encoding"></a>   
### <a name="encoding"></a>Codierung  
 Die Codierung von unterstützten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sind [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 und UTF-8. Die Codierung-Anweisung befindet sich am Anfang der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dokument. Wenn kein Codierungsattribut und keine Bytereihenfolge vorhanden ist, wird der Parser automatisch auf UTF-8 festgelegt. UTF-8 und UTF-16 sind die bevorzugten Codierungen. UTF-7 wird nicht unterstützt. Das folgende Beispiel zeigt, wie eine UTF-8-Codierung eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei.  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### <a name="language-attribute"></a>Sprachattribut  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]verwendet [XML: lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) zur Darstellung der Language-Attribut eines Elements.  Nutzen der <xref:System.Globalization.CultureInfo> -Klasse, die Language-Attributwert muss einer der vordefinierten Kulturnamen werden <xref:System.Globalization.CultureInfo>. [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) ist in der Elementstruktur vererbbar (durch XML-Regeln, nicht unbedingt wegen der Vererbung einer Abhängigkeitseigenschaft) und sein Standardwert ist eine leere Zeichenfolge, wenn sie nicht explizit zugeordnet wurde.  
  
 Das Sprachattribut ist für die Angabe von Dialekten sehr nützlich. Französisch verfügt z.B. über Schreibweisen, Vokabular und Aussprache, die in Frankreich, Quebec, Belgien und der Schweiz unterschiedlich sein können. Auch Chinesisch, Japanisch und Koreanisch freigeben Codepunkte [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], aber die ideografischen Formen unterscheiden und völlig unterschiedliche Schriftarten.  
  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel verwendet die `fr-CA` Sprachattribut Französisch (Kanada) angeben.  
  
```xml  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### <a name="unicode"></a>Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]unterstützt alle [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] Funktionen, einschließlich der Ersatzzeichen. Solange der Zeichensatz zugeordnet werden kann [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], wird unterstützt. Z.B. führt GB18030 einige Zeichen, die der Erweiterung A und B von Chinesisch, Japanisch und Koreanisch (CFK) zugeordnet sind, und Ersatzpaare ein. Daher wird es vollständig unterstützt. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung können <xref:System.Globalization.StringInfo> zum Bearbeiten von Zeichenfolgen ohne zu wissen, ob sie Ersatzzeichenpaare oder Kombinationszeichen.  
  
<a name="design_intl_ui_with_xaml"></a>   
## <a name="designing-an-international-user-interface-with-xaml"></a>Entwerfen einer internationalen Benutzeroberfläche mit XAML  
 In diesem Abschnitt wird beschrieben, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Funktionen, die Sie berücksichtigen sollten, wenn eine Anwendung schreiben.  
  
<a name="intl_text"></a>   
### <a name="international-text"></a>Internationaler Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält integrierte Verarbeitung für alle [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] Schriftsystemen unterstützt.  
  
 Die folgenden Skripts werden zurzeit unterstützt:  
  
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
  
-   Latein  
  
-   Malayalam  
  
-   Mongolisch  
  
-   Odia  
  
-   Syrisch  
  
-   Tamil  
  
-   Telugu  
  
-   Thaana  
  
-   Thailändisch*  
  
-   Tibetisch  
  
 *In dieser Version werden die Anzeige und Bearbeitung von thailändischem Text unterstützt. Die Wörtertrennung wird nicht unterstützt.  
  
 Die folgenden Skripts werden zurzeit nicht unterstützt:  
  
-   Khmer  
  
-   Koreanisch Old Hangul  
  
-   Myanmar  
  
-   Singhalesisch  
  
 Das Schriftsystem engines Unterstützung [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]Schriftarten zählen die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Layouttabellen, die Schriftart Ersteller so entwerfen Sie eine bessere Leistung internationale und High-End-typografische-Schriftarten zu ermöglichen. Die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Schriftart Layouttabellen enthalten Informationen über Glyphe Ersetzungen, Glyphe positionieren, Ausrichtung und Baseline Positionierung, aktivieren Textverarbeitung Anwendungen für den Textlayout zu verbessern.  
  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]Schriftarten können die Behandlung von großen Glyphe Sätze unter Verwendung von [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] Codierung. Diese Codierung gewährleistet eine umfassende internationale Unterstützung sowie typografische Symbolvarianten.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Textrendering beruht [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] Sub-Pixel-Technologie, die Unabhängigkeit von der Auflösung unterstützt. Dies verbessert die Lesbarkeit erheblich und bietet die Möglichkeit der Unterstützung für hochwertige Dokumente im Magazinstil für alle Skripts.  
  
<a name="intl_layout"></a>   
### <a name="international-layout"></a>Internationales Layout  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine einfache Möglichkeit für die Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In zu testendes Präsentationsframework der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft kann verwendet werden, um das Layout zu definieren. Die Muster der Flussrichtung sind:  
  
-   *LeftToRight*: Horizontales Layout für Latein, Ostasiatisch usw.  
  
-   *RightToLeft*: Bidirektional für Arabisch, Hebräisch usw.  
  
<a name="developing_localizable_apps"></a>   
## <a name="developing-localizable-applications"></a>Entwickeln von lokalisierbaren Anwendungen  
 Wenn Sie eine Anwendung für die weltweite Nutzung schreiben, sollten Sie bedenken, dass die Anwendung lokalisierbar sein muss. Die folgenden Themen zeigen Punkte auf, die zu berücksichtigen sind.  
  
<a name="mui"></a>   
### <a name="multilingual-user-interface"></a>Multilingual User Interface  
 Multilingual User Interfaces (MUI) ist ein [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] Unterstützung für den Wechsel [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] von einer Sprache in eine andere. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung verwendet das Assemblymodell zur Unterstützung von MUI. Eine Anwendung enthält sprachneutrale Assemblys sowie sprachabhängige Satellitenressourcenassemblys. Der Einstiegspunkt ist eine verwaltete EXE-Datei in der Hauptassembly.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Ressourcenladeprogramm nutzt die [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]des Ressourcen-Manager, um der Ressourcensuche und Fallback zu unterstützen. Mehrere Sprachsatellitenassemblys arbeiten mit derselben Hauptassembly. Hängt von die Ressourcenassembly, die geladen wird die <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> des aktuellen Threads.  
  
<a name="localizable_ui"></a>   
### <a name="localizable-user-interface"></a>Lokalisierbare Benutzeroberfläche  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Verwenden Sie die Anwendungen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definieren ihre [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ermöglicht es Entwicklern, eine Hierarchie von Objekten mit einem Satz von Eigenschaften und Logik anzugeben. Der primäre Verwendungszweck [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Entwicklung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sondern Anwendungen genutzt werden, geben Sie eine Hierarchie von einer [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte. Die meisten Entwickler verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] an ihre Anwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und verwenden einen Programmiersprache Ihrer Wahl, z. B. [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] auf Benutzerinteraktionen reagieren.  
  
 Aus Sicht des eine Ressource eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei beschreiben eine sprachabhängig [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Resource-Elements ist und aus diesem Grund muss das endgültige Verteilung-Format für die Unterstützung internationaler Sprachen lokalisiert werden. Da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ereignisse nicht behandeln viele [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Anwendungen enthalten Codeblöcke dazu. Weitere Informationen finden Sie unter [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md). Code entfernt und in verschiedenen Binärdateien kompiliert wird bei einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei wird in die BAML-Form von XAML in Token übersetzt. Die BAML-Form von XAML-Dateien, Bilder und andere verwaltete Ressourcenobjekte werden in die Satellitenressourcenassembly, die in andere Sprachen lokalisiert werden kann, oder in die Hauptassembly eingebettet, wenn keine Lokalisierung erforderlich ist.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Anwendungen unterstützen alle die [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Ressourcen einschließlich Zeichenfolgentabellen, Bilder und So weiter.  
  
<a name="building_localizable_apps"></a>   
### <a name="building-localizable-applications"></a>Erstellen von lokalisierbaren Anwendungen  
 Lokalisierung bezeichnet die Anpassung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] auf unterschiedliche Kulturen. Vornehmen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung lokalisiert werden kann. Entwickler müssen alle lokalisierbaren Ressourcen in einer Ressourcenassembly zu erstellen. Die Ressourcenassembly wird in verschiedenen Sprachen lokalisiert und das Code-Behind-Modell verwendet ressourcenverwaltung [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] geladen. Eine der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (".proj"). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Das folgende Beispiel einer CSPROJ-Datei zeigt die dazu erforderliche Vorgehensweise.  
  
```xml  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 Verwenden eine Ressource in der Anwendung instanziiert einen <xref:System.Resources.ResourceManager> und Laden Sie die Ressource, die Sie verwenden möchten. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## <a name="using-clickonce-with-localized-applications"></a>Verwendung von ClickOnce mit lokalisierten Anwendungen  
 ClickOnce wird eine neue Windows Forms-bereitstellungstechnologie, mit der Lieferumfang wird [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]. Es ermöglicht die Anwendungsinstallation und die Aktualisierung von Webanwendungen. Wenn eine mit ClickOnce bereitgestellte Anwendung lokalisiert ist, kann sie nur in der lokalisierten Kultur angezeigt werden. Z. B. wenn eine bereitgestellte Anwendung in Japanisch lokalisiert ist es nur angezeigt werden auf Japanisch [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] nicht auf Englisch [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)]. Dies stellt ein Problem dar, da es sich um ein übliches Szenario für japanische Benutzer zum Ausführen einer englischen Version von ist [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  
  
 Die Lösung für dieses Problem ist die Festlegung des Attributs der neutralen Fallbacksprache. Ein Anwendungsentwickler kann optional Ressourcen aus der Hauptassembly entfernen und angeben, dass die Ressourcen in einer Satellitenassembly für eine bestimmte Kultur gefunden werden können. Die Verwendung dieses Prozesses steuern die <xref:System.Resources.NeutralResourcesLanguageAttribute>. Der Konstruktor der der <xref:System.Resources.NeutralResourcesLanguageAttribute> -Klasse verfügt über zwei Signaturen, die akzeptiert ein <xref:System.Resources.UltimateResourceFallbackLocation> Parameter, um den Speicherort anzugeben, in dem die <xref:System.Resources.ResourceManager> die Fallbackressourcen extrahieren soll: Hauptassembly oder Satellitenassembly. Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden. Bei der endgültigen Ausweichpfad der Code veranlasst die <xref:System.Resources.ResourceManager> für die Ressourcen im Unterverzeichnis "de" im Verzeichnis der aktuell ausgeführten Assembly gesucht werden soll.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über WPF-Globalisierung und -Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
