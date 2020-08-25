---
title: Globalisierung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 2d7cf73e37fe8c4bbdbef3d356f1dbb8903815f3
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812327"
---
# <a name="globalization-for-wpf"></a>Globalisierung für WPF
In diesem Thema werden Probleme vorgestellt, die Sie beim Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen für den globalen Markt berücksichtigen sollten. Die Globalisierungs Programmier Elemente werden in .net im- <xref:System.Globalization> Namespace definiert.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>XAML-Globalisierung
 Extensible Application Markup Language (XAML) basiert auf XML und nutzt die in der XML-Spezifikation definierte Globalisierungs Unterstützung. In den folgenden Abschnitten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden einige Features beschrieben, die Sie kennen sollten.

<a name="char_reference"></a>
### <a name="character-references"></a>Zeichenverweise
Ein Zeichen Verweis gibt die UTF16-Code Einheit des bestimmten Unicode-Zeichens, das es darstellt, entweder in Dezimal oder hexadezimal. Das folgende Beispiel zeigt eine dezimale Zeichenreferenz für den kopalen Großbuchstaben Hori oder ' Ϩ ':

```xaml
&#1000;
```

Das folgende Beispiel zeigt einen hexadezimalen Zeichen Verweis. Beachten Sie, dass ein **x** vor der hexadezimal Zahl steht.

```xaml
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Codierung
 Die von unterstützte Codierung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sind ASCII, Unicode UTF-16 und UTF-8. Die Encoding-Anweisung befindet sich am Anfang des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dokuments. Wenn kein Codierungsattribut und keine Bytereihenfolge vorhanden ist, wird der Parser automatisch auf UTF-8 festgelegt. UTF-8 und UTF-16 sind die bevorzugten Codierungen. UTF-7 wird nicht unterstützt. Im folgenden Beispiel wird veranschaulicht, wie eine UTF-8-Codierung in einer Datei angegeben wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>Sprachattribut
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet [XML: lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) , um das sprach Attribut eines Elements darzustellen.  Um von der-Klasse profitieren zu können <xref:System.Globalization.CultureInfo> , muss der Wert des sprach Attributs einer der von vordefinierten Kultur Namen sein <xref:System.Globalization.CultureInfo> . [xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) ist in der Elementstruktur vererbbar (durch XML-Regeln, nicht unbedingt wegen der Vererbung einer Abhängigkeitseigenschaft) und sein Standardwert ist eine leere Zeichenfolge, wenn sie nicht explizit zugeordnet wurde.

 Das Sprachattribut ist für die Angabe von Dialekten sehr nützlich. Französisch verfügt z.B. über Schreibweisen, Vokabular und Aussprache, die in Frankreich, Quebec, Belgien und der Schweiz unterschiedlich sein können. Außerdem teilen Chinesisch, Japanisch und Koreanisch Code Punkte in Unicode, aber die ideografischen Formen sind unterschiedlich und verwenden vollkommen unterschiedliche Schriftarten.

 Im folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel wird das `fr-CA` Language-Attribut verwendet, um Französisch (Kanada) anzugeben.

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>Unicode
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützt alle Unicode-Features einschließlich Surrogates. Solange der Zeichensatz Unicode zugeordnet werden kann, wird er unterstützt. Z.B. führt GB18030 einige Zeichen, die der Erweiterung A und B von Chinesisch, Japanisch und Koreanisch (CFK) zugeordnet sind, und Ersatzpaare ein. Daher wird es vollständig unterstützt. Eine- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung kann verwenden <xref:System.Globalization.StringInfo> , um Zeichen folgen zu bearbeiten, ohne zu verstehen, ob Sie Ersatz Zeichenpaare oder Kombinations Zeichen aufweisen

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>Entwerfen einer internationalen Benutzeroberfläche mit XAML
 In diesem Abschnitt werden [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] die Funktionen beschrieben, die beim Schreiben einer Anwendung berücksichtigt werden sollten.

<a name="intl_text"></a>
### <a name="international-text"></a>Internationaler Text
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] schließt die integrierte Verarbeitung für alle unterstützten Schreibsysteme des Microsoft .NET Frameworks ein.

 Die folgenden Skripts werden zurzeit unterstützt:

- Arabisch

- Bengali

- Devanagari

- Kyrillisch

- Griechisch

- Gujarati

- Gurmukhi

- Hebräisch

- Ideografische Skripts

- Kannada

- Laotisch

- Lateinisch

- Malayalam

- Mongolisch

- Odia

- Syrisch

- Tamilisch

- Telugu

- Thaana

- Thailändisch*

- Tibetisch

 *In dieser Version werden die Anzeige und Bearbeitung von thailändischem Text unterstützt. Die Wörtertrennung wird nicht unterstützt.

 Die folgenden Skripts werden zurzeit nicht unterstützt:

- Khmer

- Koreanisch Old Hangul

- Myanmar

- Singhalesisch

 Alle Schreibsystem-Engines unterstützen OpenType-Schriftarten. OpenType-Schriftarten können die OpenType-Layouttabellen enthalten, die es Schriftart Entwicklern ermöglichen, bessere internationale und High-End-typografische Schriftarten zu entwerfen. Die OpenType-Schriftart Layout-Tabellen enthalten Informationen über Symbol Ersetzungen, Symbol Positionierung, Begründung und Baseline-Positionierung, sodass Textverarbeitungsanwendungen das Text Layout verbessern können.

 OpenType-Schriftarten ermöglichen die Verarbeitung großer Glyphe mithilfe der Unicode-Codierung. Diese Codierung gewährleistet eine umfassende internationale Unterstützung sowie typografische Symbolvarianten.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Text Rendering wird von der Microsoft ClearType-subpixeltechnologie unterstützt, die die Unabhängigkeit der Lösung unterstützt. Dies verbessert die Lesbarkeit erheblich und bietet die Möglichkeit der Unterstützung für hochwertige Dokumente im Magazinstil für alle Skripts.

<a name="intl_layout"></a>
### <a name="international-layout"></a>Internationales Layout
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine einfache Möglichkeit für die Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In Presentation Framework kann die- <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft verwendet werden, um Layout zu definieren. Die Muster der Flussrichtung sind:

- *LeftToRight*: Horizontales Layout für Latein, Ostasiatisch usw.

- *RightToLeft*: Bidirektional für Arabisch, Hebräisch usw.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>Entwickeln von lokalisierbaren Anwendungen
 Wenn Sie eine Anwendung für die weltweite Nutzung schreiben, sollten Sie bedenken, dass die Anwendung lokalisierbar sein muss. Die folgenden Themen zeigen Punkte auf, die zu berücksichtigen sind.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>Multilingual User Interface
 Mehrsprachige Benutzeroberflächen (MUI) sind Microsoft-Unterstützung für den Wechsel von UIs von einer Sprache zu einer anderen. Eine- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung verwendet das Assemblymodell zur Unterstützung von MUI. Eine Anwendung enthält sprachneutrale Assemblys sowie sprachabhängige Satellitenressourcenassemblys. Der Einstiegspunkt ist eine verwaltete EXE-Datei in der Hauptassembly.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Ressourcen Lade Modul nutzt den Ressourcen-Manager des Frameworks, um die Ressourcen Suche und den Fallback zu unterstützen. Mehrere Sprachsatellitenassemblys arbeiten mit derselben Hauptassembly. Die Ressourcenassembly, die geladen wird, hängt vom <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> des aktuellen Threads ab.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>Lokalisierbare Benutzeroberfläche
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, die verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , um Ihre zu definieren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ermöglicht es Entwicklern, eine Hierarchie von Objekten mit einem Satz von Eigenschaften und Logik anzugeben. Die primäre Verwendung von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist das Entwickeln von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, kann jedoch verwendet werden, um eine Hierarchie aller Common Language Runtime (CLR)-Objekte anzugeben. Die meisten Entwickler verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , um Ihre Anwendung anzugeben, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und verwenden eine Programmiersprache, wie z. b. c#, um auf Benutzerinteraktionen zu reagieren.

 Aus Sicht der Sicht ist eine Datei, die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zum Beschreiben eines sprach abhängigen entworfen wurde, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ein Ressourcen Element. Daher muss das endgültige Verteilungs Format lokalisierbar sein, um internationale Sprachen zu unterstützen. Da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ereignisse von nicht behandelt werden können [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , enthalten viele Anwendungen Code Blöcke zu diesem Zweck. Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md). Der Code wird entfernt und in verschiedene Binärdateien kompiliert, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei in die BAML-Form von XAML mit Token versehen wird. Die BAML-Form von XAML-Dateien, Bilder und andere verwaltete Ressourcenobjekte werden in die Satellitenressourcenassembly, die in andere Sprachen lokalisiert werden kann, oder in die Hauptassembly eingebettet, wenn keine Lokalisierung erforderlich ist.

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen unterstützen alle frameworkclr-Ressourcen, einschließlich Zeichen folgen Tabellen, Bildern usw.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>Erstellen von lokalisierbaren Anwendungen
 Lokalisierung bedeutet, dass ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an verschiedene Kulturen angepasst werden soll. Um eine- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung lokalisierbar zu machen, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen. Die Ressourcenassembly wird in verschiedene Sprachen lokalisiert, und der Code Behind verwendet die Ressourcenverwaltungs-API zum Laden. Eine der erforderlichen Dateien für eine- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (. proj). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Das folgende Beispiel einer CSPROJ-Datei zeigt die dazu erforderliche Vorgehensweise.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 Wenn Sie eine Ressource in Ihrer Anwendung verwenden möchten, instanziieren Sie einen, <xref:System.Resources.ResourceManager> und laden Sie die gewünschte Ressource. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>Verwendung von ClickOnce mit lokalisierten Anwendungen
 ClickOnce ist eine neue Windows Forms Bereitstellungs Technologie, die mit Visual Studio 2005 ausgeliefert wird. Es ermöglicht die Anwendungsinstallation und die Aktualisierung von Webanwendungen. Wenn eine mit ClickOnce bereitgestellte Anwendung lokalisiert ist, kann sie nur in der lokalisierten Kultur angezeigt werden. Wenn eine bereitgestellte Anwendung z. b. in Japanisch lokalisiert ist, kann Sie nur auf japanischen Microsoft Windows-Fenstern angezeigt werden, nicht in englischen Fenstern. Dies stellt ein Problem dar, da es ein gängiges Szenario für japanische Benutzer ist, eine englische Version von Windows auszuführen.

 Die Lösung für dieses Problem ist die Festlegung des Attributs der neutralen Fallbacksprache. Ein Anwendungsentwickler kann optional Ressourcen aus der Hauptassembly entfernen und angeben, dass die Ressourcen in einer Satellitenassembly für eine bestimmte Kultur gefunden werden können. Um diesen Prozess zu steuern, verwenden Sie die <xref:System.Resources.NeutralResourcesLanguageAttribute> . Der Konstruktor der- <xref:System.Resources.NeutralResourcesLanguageAttribute> Klasse verfügt über zwei Signaturen: eine, die einen-Parameter annimmt, <xref:System.Resources.UltimateResourceFallbackLocation> um den Speicherort anzugeben, an dem die <xref:System.Resources.ResourceManager> Fall Back Ressourcen extrahieren soll: Hauptassembly oder Satellitenassembly. Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden. Für den endgültigen Fall Back Speicherort bewirkt der Code, <xref:System.Resources.ResourceManager> dass die Ressourcen im Unterverzeichnis "de" des Verzeichnisses der aktuell ausgeführten Assembly sucht.

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über WPF-Globalisierung und -Lokalisierung](wpf-globalization-and-localization-overview.md)
