---
title: Globalisierung für WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 32caf87435e23008f9f300d231c2705e7894280f
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291462"
---
# <a name="globalization-for-wpf"></a>Globalisierung für WPF
In diesem Thema werden Probleme vorgestellt, die beim Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen für den globalen Markt zu beachten sind. Die Globalisierungs Programmier Elemente werden in .net im <xref:System.Globalization>-Namespace definiert.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>XAML-Globalisierung
 Extensible Application Markup Language (XAML) basiert auf [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] und nutzt die in der Spezifikation [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] definierte Globalisierungs Unterstützung. In den folgenden Abschnitten werden einige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Funktionen beschrieben, die Sie kennen sollten.

<a name="char_reference"></a>
### <a name="character-references"></a>Zeichenverweise
Ein Zeichen Verweis gibt die UTF16-Code Einheit des bestimmten [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]-Zeichens, das es darstellt, entweder in Dezimal oder hexadezimal. Das folgende Beispiel zeigt eine dezimale Zeichenreferenz für den kopalen Großbuchstaben Hori oder ' Ϩ ':

```
&#1000;
```

Das folgende Beispiel zeigt einen hexadezimalen Zeichen Verweis. Beachten Sie, dass ein **x** vor der hexadezimal Zahl steht.

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Codierung
 Die von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützte Codierung sind ASCII-, [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]-UTF-16-und UTF-8-Codierung. Die Encoding-Anweisung befindet sich am Anfang [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dokuments. Wenn kein Codierungsattribut und keine Bytereihenfolge vorhanden ist, wird der Parser automatisch auf UTF-8 festgelegt. UTF-8 und UTF-16 sind die bevorzugten Codierungen. UTF-7 wird nicht unterstützt. Im folgenden Beispiel wird veranschaulicht, wie eine UTF-8-Codierung in einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei angegeben wird.

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>Sprachattribut
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet [XML: lang](../../xaml-services/xml-lang-handling-in-xaml.md) , um das sprach Attribut eines Elements darzustellen.  Um die <xref:System.Globalization.CultureInfo>-Klasse zu nutzen, muss der Wert des sprach Attributs einer der von <xref:System.Globalization.CultureInfo> vordefinierten Kultur Namen sein. [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) ist in der Elementstruktur vererbbar (durch XML-Regeln, nicht unbedingt wegen der Vererbung einer Abhängigkeitseigenschaft) und sein Standardwert ist eine leere Zeichenfolge, wenn sie nicht explizit zugeordnet wurde.

 Das Sprachattribut ist für die Angabe von Dialekten sehr nützlich. Französisch verfügt z.B. über Schreibweisen, Vokabular und Aussprache, die in Frankreich, Quebec, Belgien und der Schweiz unterschiedlich sein können. Außerdem teilen Chinesisch, Japanisch und Koreanisch Code Punkte in [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], aber die ideografischen Formen sind unterschiedlich und verwenden vollkommen unterschiedliche Schriftarten.

 Im folgenden Beispiel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird das sprach Attribut `fr-CA` verwendet, um Französisch (Kanada) anzugeben.

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>Unicode
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützt alle [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]-Features einschließlich Surrogates. Solange der Zeichensatz [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] zugeordnet werden kann, wird er unterstützt. Z.B. führt GB18030 einige Zeichen, die der Erweiterung A und B von Chinesisch, Japanisch und Koreanisch (CFK) zugeordnet sind, und Ersatzpaare ein. Daher wird es vollständig unterstützt. Eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung kann <xref:System.Globalization.StringInfo> verwenden, um Zeichen folgen zu bearbeiten, ohne zu verstehen, ob Sie Ersatzpaare haben oder Zeichen miteinander kombinieren.

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>Entwerfen einer internationalen Benutzeroberfläche mit XAML
 In diesem Abschnitt werden [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Funktionen beschrieben, die beim Schreiben einer Anwendung berücksichtigt werden sollten.

<a name="intl_text"></a>
### <a name="international-text"></a>Internationaler Text
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] umfasst die integrierte Verarbeitung für alle Microsoft .NET Framework-unterstützten Schreibsysteme.

 Die folgenden Skripts werden zurzeit unterstützt:

- Arabisch

- Bangla

- Devanagari

- Kyrillisch

- Griechisch

- Gujarati

- Gurmukhi

- Hebräisch

- Ideografische Skripts

- Kannada

- Laotisch

- Latein

- Malayalam

- Mongolisch

- Odia

- Syrisch

- Tamil

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

 OpenType-Schriftarten ermöglichen die Handhabung von großen Glyphe-Sätzen mithilfe [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]-Codierung. Diese Codierung gewährleistet eine umfassende internationale Unterstützung sowie typografische Symbolvarianten.

 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Text Rendering wird von der Microsoft ClearType-subpixeltechnologie unterstützt, die die Unabhängigkeit der Lösung unterstützt. Dies verbessert die Lesbarkeit erheblich und bietet die Möglichkeit der Unterstützung für hochwertige Dokumente im Magazinstil für alle Skripts.

<a name="intl_layout"></a>
### <a name="international-layout"></a>Internationales Layout
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine einfache Möglichkeit für die Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In Presentation Framework kann die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft verwendet werden, um das Layout zu definieren. Die Muster der Flussrichtung sind:

- *LeftToRight*: Horizontales Layout für Latein, Ostasiatisch usw.

- *RightToLeft*: Bidirektional für Arabisch, Hebräisch usw.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>Entwickeln von lokalisierbaren Anwendungen
 Wenn Sie eine Anwendung für die weltweite Nutzung schreiben, sollten Sie bedenken, dass die Anwendung lokalisierbar sein muss. Die folgenden Themen zeigen Punkte auf, die zu berücksichtigen sind.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>Multilingual User Interface
 Mehrsprachige Benutzeroberflächen (MUI) sind Microsoft-Unterstützung für den Wechsel von UIs von einer Sprache zu einer anderen. Eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung verwendet das Assemblymodell zur Unterstützung von MUI. Eine Anwendung enthält sprachneutrale Assemblys sowie sprachabhängige Satellitenressourcenassemblys. Der Einstiegspunkt ist eine verwaltete EXE-Datei in der Hauptassembly.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ressourcen Lader nutzt den Ressourcen-Manager von [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)], um die Ressourcen Suche und den Fallback zu unterstützen. Mehrere Sprachsatellitenassemblys arbeiten mit derselben Hauptassembly. Die Ressourcenassembly, die geladen wird, hängt vom <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> des aktuellen Threads ab.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>Lokalisierbare Benutzeroberfläche
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], um deren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zu definieren. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ermöglicht es Entwicklern, eine Hierarchie von Objekten mit einem Satz von Eigenschaften und Logik anzugeben. Die primäre Verwendung von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Entwicklung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen, kann jedoch verwendet werden, um eine Hierarchie beliebiger Common Language Runtime (CLR)-Objekte anzugeben. Die meisten Entwickler verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], um die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung anzugeben, und verwenden eine Programmier C# Sprache wie, um auf die Benutzerinteraktion zu reagieren.

 Aus Sicht der Sicht ist eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei, die für die Beschreibung eines sprach abhängigen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] konzipiert ist, ein Ressourcen Element. Daher muss das endgültige Verteilungs Format lokalisiert werden können, um internationale Sprachen zu unterstützen. Da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ereignisse nicht verarbeiten kann, enthalten viele [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendungen Code Blöcke, um dies zu tun. Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](xaml-overview-wpf.md). Der Code wird entfernt und in verschiedene Binärdateien kompiliert, wenn eine Datei mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der BAML-Form von XAML mit Token versehen wird. Die BAML-Form von XAML-Dateien, Bilder und andere verwaltete Ressourcenobjekte werden in die Satellitenressourcenassembly, die in andere Sprachen lokalisiert werden kann, oder in die Hauptassembly eingebettet, wenn keine Lokalisierung erforderlich ist.

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen unterstützen alle [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]clr-Ressourcen, einschließlich Zeichen folgen Tabellen, Images usw.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>Erstellen von lokalisierbaren Anwendungen
 Lokalisierung bedeutet, dass ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an verschiedene Kulturen angepasst wird. Um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung lokalisierbar zu machen, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen. Die Ressourcenassembly wird in verschiedene Sprachen lokalisiert, und der Code Behind verwendet die Ressourcenverwaltungs-API zum Laden. Eine der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung ist eine Projektdatei (. proj). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Das folgende Beispiel einer CSPROJ-Datei zeigt die dazu erforderliche Vorgehensweise.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 Wenn Sie eine Ressource in Ihrer Anwendung verwenden möchten, instanziieren Sie eine <xref:System.Resources.ResourceManager>, und laden Sie die Ressource, die Sie verwenden möchten. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>Verwendung von ClickOnce mit lokalisierten Anwendungen
 ClickOnce ist eine neue Windows Forms Bereitstellungs Technologie, die mit Visual Studio 2005 ausgeliefert wird. Es ermöglicht die Anwendungsinstallation und die Aktualisierung von Webanwendungen. Wenn eine mit ClickOnce bereitgestellte Anwendung lokalisiert ist, kann sie nur in der lokalisierten Kultur angezeigt werden. Wenn eine bereitgestellte Anwendung z. b. in Japanisch lokalisiert ist, kann Sie nur auf Japanisch angezeigt werden [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] nicht in englischen Fenstern. Dies stellt ein Problem dar, da es ein gängiges Szenario für japanische Benutzer ist, eine englische Version von Windows auszuführen.

 Die Lösung für dieses Problem ist die Festlegung des Attributs der neutralen Fallbacksprache. Ein Anwendungsentwickler kann optional Ressourcen aus der Hauptassembly entfernen und angeben, dass die Ressourcen in einer Satellitenassembly für eine bestimmte Kultur gefunden werden können. Um diesen Prozess zu steuern, verwenden Sie den <xref:System.Resources.NeutralResourcesLanguageAttribute>. Der Konstruktor der <xref:System.Resources.NeutralResourcesLanguageAttribute>-Klasse verfügt über zwei Signaturen: eine, die einen <xref:System.Resources.UltimateResourceFallbackLocation>-Parameter annimmt, um den Speicherort anzugeben, an dem die <xref:System.Resources.ResourceManager> die Fall Back Ressourcen extrahieren soll: Hauptassembly oder Satellitenassembly. Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden. Für den endgültigen Fall Back Speicherort bewirkt der Code, dass die <xref:System.Resources.ResourceManager> nach den Ressourcen im Unterverzeichnis "de" des Verzeichnisses der aktuell ausgeführten Assembly sucht.

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über WPF-Globalisierung und -Lokalisierung](wpf-globalization-and-localization-overview.md)
