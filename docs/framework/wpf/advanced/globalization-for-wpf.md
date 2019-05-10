---
title: Globalisierung für WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: bfd901d10fe3158c1c5cb32c3a75f3bc15efd0ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640938"
---
# <a name="globalization-for-wpf"></a>Globalisierung für WPF
In diesem Thema werden Probleme, die Sie beim Schreiben von bewusst sein sollten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen für den globalen Markt. Programmierelemente der Globalisierung werden in definiert [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization`.

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>XAML-Globalisierung
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] basiert auf [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] und nutzt die Vorteile der globalisierungsunterstützung im definiert die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Spezifikation. Die folgenden Abschnitte beschreiben einige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Features, die Sie kennen sollten.

<a name="char_reference"></a>
### <a name="character-references"></a>Zeichenverweise
Ein Zeichenverweis gibt die Einheit des UTF16-Code des entsprechenden [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] -Zeichen im Dezimal- oder Hexadezimalformat. Das folgende Beispiel zeigt einen Verweis mit Dezimalzeichen für KOPTISCH CAPITAL LETTER HORI oder "Ϩ":

```
&#1000;
```

Das folgende Beispiel zeigt einen Verweis mit Hexadezimalzeichen. Beachten Sie, dass es eine **x** vor der Hexadezimalzahl steht.

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Codierung
 Die Codierung von unterstützten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sind [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16 und UTF-8. Die codierungsanweisung befindet sich am Anfang des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dokument. Wenn kein Codierungsattribut und keine Bytereihenfolge vorhanden ist, wird der Parser automatisch auf UTF-8 festgelegt. UTF-8 und UTF-16 sind die bevorzugten Codierungen. UTF-7 wird nicht unterstützt. Das folgende Beispiel zeigt, wie eine UTF-8-Codierung in eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei.

```
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>Sprachattribut
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet [XML: lang](../../xaml-services/xml-lang-handling-in-xaml.md) der Language-Attribut eines Elements darstellen.  Nutzen der <xref:System.Globalization.CultureInfo> -Klasse, der Sprachattributwert muss einer der von vordefinierten Kulturnamen sein <xref:System.Globalization.CultureInfo>. [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) ist in der Elementstruktur vererbbar (durch XML-Regeln, nicht unbedingt wegen der Vererbung einer Abhängigkeitseigenschaft) und sein Standardwert ist eine leere Zeichenfolge, wenn sie nicht explizit zugeordnet wurde.

 Das Sprachattribut ist für die Angabe von Dialekten sehr nützlich. Französisch verfügt z.B. über Schreibweisen, Vokabular und Aussprache, die in Frankreich, Quebec, Belgien und der Schweiz unterschiedlich sein können. Auch Chinesisch, Japanisch und Koreanisch teilen sich Codepunkte im [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], aber die ideografischen Formen unterscheiden, und sie verwenden vollkommen unterschiedliche Schriftarten.

 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel verwendet die `fr-CA` Language-Attribut, um Französisch (Kanada) anzugeben.

```xml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>Unicode
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützt alle [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] Features, einschließlich der Ersatzzeichen. Solange der Zeichensatz zugeordnet werden kann [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], wird unterstützt. Z.B. führt GB18030 einige Zeichen, die der Erweiterung A und B von Chinesisch, Japanisch und Koreanisch (CFK) zugeordnet sind, und Ersatzpaare ein. Daher wird es vollständig unterstützt. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung können <xref:System.Globalization.StringInfo> Zeichenfolgen bearbeiten, ohne zu wissen, ob sie Ersatzzeichenpaare oder Verbindungszeichen.

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>Entwerfen einer internationalen Benutzeroberfläche mit XAML
 In diesem Abschnitt wird beschrieben, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Funktionen, die Sie berücksichtigen sollten, wenn eine Anwendung schreiben.

<a name="intl_text"></a>
### <a name="international-text"></a>Internationaler Text
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält integrierte Verarbeitung für alle Microsoft .NET Framework unterstützt das Schreiben von Systemen.

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

 Alle Schreibsystem-engines unterstützen [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Schriftarten zählen die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Layouttabellen, mit denen Ersteller von Schriftarten bessere internationale und Highend-typografische-Schriftarten entwerfen können. Die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Layouttabellen der Schriftart enthalten Informationen über symbolersetzungen, symbolpositionierung, Ausrichtung und Positionierung Textverarbeitungstools Anwendungen Textlayout zu verbessern.

 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] -Schriftarten ermöglichen die Behandlung großer Symbolsätze Sätze unter Verwendung von [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] Codierung. Diese Codierung gewährleistet eine umfassende internationale Unterstützung sowie typografische Symbolvarianten.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Rendern von Text basiert auf [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] Subpixel-Technologie, die Unabhängigkeit von der Auflösung unterstützt. Dies verbessert die Lesbarkeit erheblich und bietet die Möglichkeit der Unterstützung für hochwertige Dokumente im Magazinstil für alle Skripts.

<a name="intl_layout"></a>
### <a name="international-layout"></a>Internationales Layout
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine einfache Möglichkeit für die Unterstützung von horizontalen, bidirektionalen und vertikalen Layouts. In PresentationFramework der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft kann verwendet werden, um das Layout zu definieren. Die Muster der Flussrichtung sind:

- *LeftToRight*: Horizontales Layout für Latein, Ostasiatisch usw.

- *RightToLeft*: Bidirektional für Arabisch, Hebräisch usw.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>Entwickeln von lokalisierbaren Anwendungen
 Wenn Sie eine Anwendung für die weltweite Nutzung schreiben, sollten Sie bedenken, dass die Anwendung lokalisierbar sein muss. Die folgenden Themen zeigen Punkte auf, die zu berücksichtigen sind.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>Multilingual User Interface
 Multilingual User Interfaces (MUI) ist eine [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] -Support für einen Wechsel [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] von einer Sprache in eine andere. Ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung verwendet das Assemblymodell zur Unterstützung von MUI. Eine Anwendung enthält sprachneutrale Assemblys sowie sprachabhängige Satellitenressourcenassemblys. Der Einstiegspunkt ist eine verwaltete EXE-Datei in der Hauptassembly.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Ressourcenladeprogramm nutzt die [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]des Ressourcen-Manager zur Unterstützung der Ressourcensuche und Fallback. Mehrere Sprachsatellitenassemblys arbeiten mit derselben Hauptassembly. Die Ressourcenassembly, die geladen wird hängt von der <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> des aktuellen Threads.

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>Lokalisierbare Benutzeroberfläche
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definieren ihre [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ermöglicht es Entwicklern, eine Hierarchie von Objekten mit einem Satz von Eigenschaften und Logik anzugeben. Der primäre Verwendungszweck [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Entwicklung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, aber sie können verwendet werden, um eine Hierarchie von angeben [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte. Die meisten Entwickler verwenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] an ihrer Anwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und eine Programmiersprache wie c# verwenden, um auf Benutzerinteraktionen reagieren.

 Aus Sicht einer Ressource eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, die eine sprachabhängige beschrieben [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ist ein Ressourcenelement und daher muss sein fertiges verteilungsformat lokalisierbar, um internationale Sprachen zu unterstützen. Da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ereignisse nicht behandeln viele [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Anwendungen enthalten, Blöcke von Code für diese Aufgabe. Weitere Informationen finden Sie unter [XAML Overview (WPF)](xaml-overview-wpf.md). Code wird entfernt und in verschiedene Binärdateien kompiliert beim eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei in der BAML-Form von XAML mit Token versehen wird. Die BAML-Form von XAML-Dateien, Bilder und andere verwaltete Ressourcenobjekte werden in die Satellitenressourcenassembly, die in andere Sprachen lokalisiert werden kann, oder in die Hauptassembly eingebettet, wenn keine Lokalisierung erforderlich ist.

> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungen unterstützen alle die [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Ressourcen einschließlich Zeichenfolgentabellen, Bilder und So weiter.

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>Erstellen von lokalisierbaren Anwendungen
 Lokalisierung bezeichnet die Anpassung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für andere Kulturen. Zu einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung lokalisierbar sein, müssen Entwickler alle lokalisierbaren Ressourcen in einer Ressourcenassembly erstellen. Die Ressourcenassembly wird in verschiedenen Sprachen lokalisiert, und das CodeBehind verwendet die ressourcenverwaltung [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] geladen. Einer der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (.proj). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Das folgende Beispiel einer CSPROJ-Datei zeigt die dazu erforderliche Vorgehensweise.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 Verwenden eine Ressource in Ihrer Anwendung Instanziieren einer <xref:System.Resources.ResourceManager> und Laden Sie die Ressource, die Sie verwenden möchten. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>Verwendung von ClickOnce mit lokalisierten Anwendungen
 ClickOnce ist eine neue Windows Forms-bereitstellungstechnologie, die mit Visual Studio 2005 ausgeliefert wird. Es ermöglicht die Anwendungsinstallation und die Aktualisierung von Webanwendungen. Wenn eine mit ClickOnce bereitgestellte Anwendung lokalisiert ist, kann sie nur in der lokalisierten Kultur angezeigt werden. Z. B. wenn eine bereitgestellte Anwendung in Japanisch lokalisiert ist kann nur angesehen werden in der japanischen Version [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] nicht auf Englisch Windows. Dies stellt ein Problem, da es ein gängiges Szenario für japanische Benutzer eine englische Version von Windows ausgeführt wird.

 Die Lösung für dieses Problem ist die Festlegung des Attributs der neutralen Fallbacksprache. Ein Anwendungsentwickler kann optional Ressourcen aus der Hauptassembly entfernen und angeben, dass die Ressourcen in einer Satellitenassembly für eine bestimmte Kultur gefunden werden können. Die Verwendung dieses Prozesses steuern die <xref:System.Resources.NeutralResourcesLanguageAttribute>. Der Konstruktor der der <xref:System.Resources.NeutralResourcesLanguageAttribute> -Klasse verfügt über zwei Signaturen, die akzeptiert eine <xref:System.Resources.UltimateResourceFallbackLocation> Parameter, um den Speicherort anzugeben, in denen die <xref:System.Resources.ResourceManager> die Fallbackressourcen extrahieren soll: Hauptassembly oder Satellitenassembly. Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden. Für den endgültigen Ausweichpfad bewirkt der Code die <xref:System.Resources.ResourceManager> , für die Ressourcen im Unterverzeichnis "de" des Verzeichnisses der aktuell ausgeführten Assembly zu suchen.

```
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über WPF-Globalisierung und -Lokalisierung](wpf-globalization-and-localization-overview.md)
