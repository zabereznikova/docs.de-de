---
title: Übersicht über Flussdokumente
description: Erfahren Sie mehr über Fluss Dokumente in Windows Presentation Foundation, die Inhalte basierend auf Fenstergröße, Geräte Auflösung und Benutzereinstellungen dynamisch anpassen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: dac0cb91175a1398a0124020c048e14d7bcd1f76
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165236"
---
# <a name="flow-document-overview"></a>Übersicht über Flussdokumente

Flussdokumente dienen der Optimierung der Anzeige und Lesbarkeit. Flussdokumente sind nicht auf ein vordefiniertes Layout festgelegt, sondern passen ihren Inhalt auf Grundlage von Laufzeitvariablen wie Fenstergröße, Geräteauflösung und optionalen Benutzereinstellungen dynamisch an und brechen ihn dynamisch um. Zudem bieten Flussdokumente erweiterte Dokumentfunktionen, z.B. Paginierung und Spalten. Dieses Thema enthält eine Übersicht über Flussdokumente und deren Erstellung.

<a name="what_is_a_flow_document"></a>

## <a name="what-is-a-flow-document"></a>Was ist ein Flussdokument?

Ein Flussdokument wurde konzipiert, um abhängig von der Fenstergröße, der Geräteauflösung und anderen Umgebungsvariablen den „Inhalt dynamisch umzubrechen“. Zudem verfügen Flussdokumente über eine Vielzahl integrierter Funktionen, inklusive der Suche, Anzeigemodi zur Optimierung der Lesbarkeit und der Möglichkeit zum Ändern der Größe und Darstellung von Schriftarten. Flussdokumente werden am besten verwendet, wenn das erleichterte Lesen das Hauptgebrauchsszenario des Dokuments darstellt. Im Gegensatz dazu sind fixierte Dokumente für eine statische Darstellung entworfen. Fixierte Dokumente sind hilfreich, wenn die Originaltreue des Quellinhalts wichtig ist. Weitere Informationen zu verschiedenen Dokumenttypen finden Sie unter [Dokumente in WPF](documents-in-wpf.md) .

Die folgende Abbildung zeigt ein Beispielflussdokument in mehreren Fenstern von verschiedener Größe. Wenn sich der Bildschirmbereich ändert, bricht der Inhalt dynamisch um, um den verfügbaren Platz bestmöglich auszunutzen.

![Flussdokument-Inhalt, geänderte Flussrichtung](./media/edocs-flowdocument.png "eDocs_FlowDocument")

Wie in dem Bild oben dargestellt, kann fortlaufender Inhalt viele Komponenten umfassen, einschließlich Absätzen, Listen, Bilder usw. Diese Komponenten entsprechen Elementen im Markup und Objekten in prozeduralem Code. Diese Klassen werden weiter unten im Abschnitt [Fluss bezogene Klassen](#flow_related_classes) dieser Übersicht ausführlich erläutert. Im folgenden finden Sie ein einfaches Codebeispiel, in dem ein Fluss Dokument erstellt wird, das aus einem Absatz mit fett formatiertem Text und einer Liste besteht.

[!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]

In der folgenden Abbildung wird gezeigt, wie dieser Codeausschnitt aussieht.

![Bildschirmabbildung: Gerendertes FlowDocument-Beispiel](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")

In diesem Beispiel wird das- <xref:System.Windows.Controls.FlowDocumentReader> Steuerelement verwendet, um den fortlaufenden Inhalt zu hosten. Weitere Informationen zu flowinhaltshostingsteuerelementen finden Sie unter [Fluss Dokumenttypen](#flow_document_types) . <xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.List>-, <xref:System.Windows.Documents.ListItem> -,-und- <xref:System.Windows.Documents.Bold> Elemente werden verwendet, um die Inhalts Formatierung basierend auf ihrer Reihenfolge im Markup zu steuern. Das- <xref:System.Windows.Documents.Bold> Element erstreckt sich z. b. nur über einen Teil des Texts im Absatz, daher ist nur dieser Teil des Texts fett formatiert. Wenn Sie HTML verwendet haben, wird Ihnen dies vertraut sein.

Wie in der obigen Abbildung hervorgehoben, gibt es mehrere Funktionen, die in Fluss Dokumente integriert sind:

- Suche: Ermöglicht dem Benutzer, eine Volltextsuche auf ein ganzes Dokument auszuführen.

- Anzeigemodus: Der Benutzer kann seinen bevorzugten Anzeigemodus auswählen, darunter der Anzeigemodus „Einzelne Seite“ (Seite-für-Seite), der Anzeigemodus „Zwei Seiten“ (Buchleseformat) und der fortlaufende Anzeigemodus „Fensterinhalt verschieben“ (unbeschränkt).  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> .

- Steuerelemente für die Seitennavigation: Wenn der Anzeigemodus des Dokuments Seiten verwendet, umfassen die Steuerelemente für die Seitennavigation eine Schaltfläche zum Springen auf die nächste Seite (Pfeil nach unten) oder die vorherige Seite (Pfeil nach oben) sowie Indikatoren für die aktuelle Seitennummer und die Gesamtzahl der Seiten. Das Blättern durch Seiten funktioniert auch mithilfe der Pfeiltasten auf der Tastatur.

- Zoom: Die Zoomsteuerelemente ermöglichen es dem Benutzer, die Zoomstufe zu erhöhen oder zu verringern, indem er entsprechend auf die Plus- oder Minusschaltfächen klickt. Die Zoomsteuerelemente umfassen zudem einen Schieberegler zum Anpassen der Zoomstufe. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.

Diese Funktionen können basierend auf dem zum Hosten des fortlaufenden Inhalts verwendeten Steuerelement bearbeitet werden. Im nächsten Abschnitt werden die verschiedenen Steuerelemente beschrieben.

<a name="flow_document_types"></a>

## <a name="flow-document-types"></a>Flussdokumenttypen

Die Anzeige und Darstellung von Flussdokumentinhalt hängt davon ab, welches Objekt zum Hosten des fortlaufenden Inhalts verwendet wird. Es gibt vier Steuerelemente, die die Anzeige von fortlaufendem Inhalt unterstützen: <xref:System.Windows.Controls.FlowDocumentReader> , <xref:System.Windows.Controls.FlowDocumentPageViewer> , <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> . Diese Steuerelemente werden nachstehend kurz beschrieben.

> [!NOTE]
> <xref:System.Windows.Documents.FlowDocument>ist erforderlich, um fortlaufenden Inhalt direkt zu hosten. Daher verwenden alle diese Anzeige Steuerelemente einen, um das Hosting von fortlaufendem <xref:System.Windows.Documents.FlowDocument> Inhalt zu

### <a name="flowdocumentreader"></a>FlowDocumentReader

<xref:System.Windows.Controls.FlowDocumentReader>enthält Funktionen, die es dem Benutzer ermöglichen, dynamisch zwischen verschiedenen Anzeigemodi zu wählen, z. b. einem einseitigen Anzeigemodus (seitenweise), einem bidirektionalen Anzeigemodus (Buch lese Format) und einem fortlaufenden Scrollmodus (in der untersten Größe). Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> . , Wenn Sie nicht in der Lage sein müssen, dynamisch zwischen verschiedenen Anzeigemodi zu wechseln, <xref:System.Windows.Controls.FlowDocumentPageViewer> und einen <xref:System.Windows.Controls.FlowDocumentScrollViewer> Auslagerungs Inhalts-Viewer mit leichteren Gewichtungen bereitstellen, die in einem bestimmten Anzeigemodus korrigiert sind.

### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer und FlowDocumentScrollViewer

<xref:System.Windows.Controls.FlowDocumentPageViewer>zeigt den Inhalt im Seiten-zu-Zeit-Anzeigemodus an, während <xref:System.Windows.Controls.FlowDocumentScrollViewer> Inhalt im fortlaufenden Scrollmodus angezeigt wird. Sowohl <xref:System.Windows.Controls.FlowDocumentPageViewer> als auch <xref:System.Windows.Controls.FlowDocumentScrollViewer> werden in einem bestimmten Anzeigemodus korrigiert. Vergleichen mit <xref:System.Windows.Controls.FlowDocumentReader> , das Funktionen enthält, die es dem Benutzer ermöglichen, sich dynamisch zwischen verschiedenen Anzeigemodi (wie von der-Enumeration bereitgestellt) zu entscheiden <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> , um ressourcenintensiver als oder zu sein <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> .

Standardmäßig wird eine vertikale Scrollleiste immer angezeigt, und eine horizontale Scrollleiste wird bei Bedarf angezeigt. Die Standardbenutzer Oberfläche für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> . die-Eigenschaft kann jedoch verwendet werden, um eine integrierte Symbolleiste zu aktivieren.

### <a name="richtextbox"></a>RichTextBox

Sie verwenden eine <xref:System.Windows.Controls.RichTextBox> , wenn Sie es dem Benutzer ermöglichen möchten, den fortlaufenden Inhalt zu bearbeiten. Wenn Sie z. b. einen Editor erstellen möchten, der es einem Benutzer ermöglicht, Elemente wie Tabellen, kursiv Formatierung und Fett Formatierung usw. zu bearbeiten, verwenden Sie eine <xref:System.Windows.Controls.RichTextBox> . Weitere Informationen finden Sie unter [Übersicht über RichTextBox](../controls/richtextbox-overview.md) .

> [!NOTE]
> Fortlaufendem Inhalt in einem <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie fortlaufenden Inhalt in anderen Steuerelementen. Beispielsweise gibt es keine Spalten in einem <xref:System.Windows.Controls.RichTextBox> und somit kein automatisches Verhalten bei der Änderung der Größe. Außerdem sind die, die in der Regel in Funktionen von fortlaufendem Inhalt wie suchen, Anzeigemodus, Seitennavigation und Zoom integriert sind, in einer nicht verfügbar <xref:System.Windows.Controls.RichTextBox> .

<a name="creating_flow_content"></a>

## <a name="creating-flow-content"></a>Erstellen von fortlaufendem Inhalt

Fortlaufendem Inhalt kann komplex sein und aus verschiedenen Elementen bestehen, einschließlich Text, Bildern, Tabellen und sogar <xref:System.Windows.UIElement> abgeleiteten Klassen wie Steuerelementen. Um zu verstehen, wie komplexer fortlaufender Inhalt erstellt wird, sind die folgenden Punkte wichtig:

- **Flussbezogene Klassen**: Jede in fortlaufendem Inhalt verwendete Klasse hat einen bestimmten Zweck. Darüber hinaus hilft Ihnen die hierarchische Beziehung zwischen Flussklassen dabei, zu verstehen, wie sie verwendet werden. Beispielsweise werden von der-Klasse abgeleitete Klassen <xref:System.Windows.Documents.Block> verwendet, um andere Objekte zu enthalten, während von abgeleitete Klassen- <xref:System.Windows.Documents.Inline> Objekte enthalten, die angezeigt werden.

- **Inhaltsschema**: Ein Flussdokument kann eine beträchtliche Anzahl von geschachtelten Elementen erfordern. Das Inhaltsschema gibt mögliche Übergeordnet/Untergeordnet-Beziehungen zwischen Elementen an.

In den folgenden Abschnitten wird jeder dieser Bereiche ausführlicher erklärt.

<a name="flow_related_classes"></a>

## <a name="flow-related-classes"></a>Flussbezogene Klassen

Das folgende Diagramm zeigt die am häufigsten bei fortlaufendem Inhalt verwendeten Objekte:

![Diagramm: Flussinhaltselement-Klassenhierarchie](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")

Für die Zwecke des fortlaufenden Inhalts gibt es zwei wichtige Kategorien:

1. **Blockabgeleitete Klassen**: Auch „Blockinhaltselemente“ oder einfach „Blockelemente“ genannt. Elemente, die von erben, <xref:System.Windows.Documents.Block> können verwendet werden, um Elemente unter einem gemeinsamen übergeordneten Element zu gruppieren oder um allgemeine Attribute auf eine Gruppe anzuwenden.

2. **Inlineabgeleitete Klassen**: Auch „Inlineinhaltselemente“ oder einfach „Inlineelemente“ genannt. Elemente, die von erben, <xref:System.Windows.Documents.Inline> sind entweder in einem Block Element oder einem anderen Inline Element enthalten. Inlineelemente werden oft als direkter Container für Inhalt verwendet, der auf dem Bildschirm gerendert wird. Ein- <xref:System.Windows.Documents.Paragraph> Element (Block-Element) kann z. b. ein- <xref:System.Windows.Documents.Run> Element (Inline Element) enthalten, aber das-Element <xref:System.Windows.Documents.Run> enthält tatsächlich den auf dem Bildschirm gerenderten Text.

Jede Klasse in diesen zwei Kategorien wird nachstehend kurz beschrieben.

### <a name="block-derived-classes"></a>Blockabgeleitete Klassen

**Abschnitt**

<xref:System.Windows.Documents.Paragraph>wird normalerweise zum Gruppieren von Inhalten in einem Absatz verwendet. Die einfachste und häufigste Verwendung von Paragraph ist, einen Textabsatz zu erstellen.

[!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]

Sie können jedoch auch andere Inline abgeleitete Elemente enthalten, wie Sie unten sehen werden.

**Bereich**

<xref:System.Windows.Documents.Section>wird nur verwendet, um andere von <xref:System.Windows.Documents.Block> abgeleitete Elemente zu enthalten. Sie wendet keine Standardformatierungen auf die Elemente an, die sie einschließt. Alle Eigenschaftswerte, die für einen festgelegt werden, <xref:System.Windows.Documents.Section> gelten jedoch für die untergeordneten Elemente. Eine Section-Klasse ermöglicht es Ihnen auch, ihre untergeordnete Auflistung programmgesteuert zu durchlaufen. <xref:System.Windows.Documents.Section>wird auf ähnliche Weise wie das- \<DIV> Tag in HTML verwendet.

Im folgenden Beispiel werden drei Absätze unter eins definiert <xref:System.Windows.Documents.Section> . Der-Wert des-Abschnitts hat den- <xref:System.Windows.Documents.TextElement.Background%2A> Eigenschafts Wert "Red", daher ist die Hintergrundfarbe der Absätze ebenfalls rot.

[!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]

**BlockUIContainer**

<xref:System.Windows.Documents.BlockUIContainer>ermöglicht <xref:System.Windows.UIElement> , dass Elemente (d. h. ein <xref:System.Windows.Controls.Button> ) in von einem Block abgeleitete fortlaufenden Inhalt eingebettet werden. <xref:System.Windows.Documents.InlineUIContainer>(siehe unten) wird zum <xref:System.Windows.UIElement> Einbetten von Elementen in Inline abgeleiteter fortlaufendem Inhalt verwendet. <xref:System.Windows.Documents.BlockUIContainer>und <xref:System.Windows.Documents.InlineUIContainer> sind wichtig, da es keine andere Möglichkeit gibt, einen in Flow-Inhalt zu verwenden, es <xref:System.Windows.UIElement> sei denn, er ist in einem dieser beiden Elemente enthalten.

Im folgenden Beispiel wird gezeigt, wie das- <xref:System.Windows.Documents.BlockUIContainer> Element zum Hosten <xref:System.Windows.UIElement> von Objekten innerhalb von fortlaufendem Inhalt verwendet wird

[!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]

Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird:

![Screenshot, der ein in fortlaufendem Inhalt eingebettetes UIElement zeigt.](./media/flow-document-overview/embedded-blockuicontainer.png)

**Liste**

<xref:System.Windows.Documents.List>dient zum Erstellen einer aufzurufenen oder numerischen Liste. Legen Sie die- <xref:System.Windows.Documents.List.MarkerStyle%2A> Eigenschaft auf einen- <xref:System.Windows.TextMarkerStyle> Enumerationswert fest, um den Stil der Liste zu bestimmen. Das folgende Beispiel zeigt, wie Sie eine einfache Liste erstellen.

[!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.List>ist das einzige Flow-Element, das verwendet, um untergeordnete <xref:System.Windows.Documents.ListItemCollection> Elemente zu verwalten.

**Table**

<xref:System.Windows.Documents.Table>wird verwendet, um eine Tabelle zu erstellen. <xref:System.Windows.Documents.Table>ähnelt dem <xref:System.Windows.Controls.Grid> -Element, verfügt jedoch über mehr Funktionen und erfordert daher einen höheren Ressourcen Aufwand. Da <xref:System.Windows.Controls.Grid> ein ist <xref:System.Windows.UIElement> , kann es nicht in fortlaufendem Inhalt verwendet werden, es sei denn, er ist in einem oder in enthalten <xref:System.Windows.Documents.BlockUIContainer> <xref:System.Windows.Documents.InlineUIContainer> . Weitere Informationen zu <xref:System.Windows.Documents.Table> finden Sie unter [Tabellen Übersicht](table-overview.md).

### <a name="inline-derived-classes"></a>Inlineabgeleitete Klassen

**Ausführen**

<xref:System.Windows.Documents.Run>wird verwendet, um unformatierten Text zu enthalten. Sie erwarten möglicherweise <xref:System.Windows.Documents.Run> , dass Objekte im fortlaufenden Inhalt häufig verwendet werden. Allerdings müssen Elemente im Markup <xref:System.Windows.Documents.Run> nicht explizit verwendet werden. <xref:System.Windows.Documents.Run>muss beim Erstellen oder Bearbeiten von Fluss Dokumenten mithilfe von Code verwendet werden. Im folgenden Markup gibt z. b. das erste <xref:System.Windows.Documents.Paragraph> explizit das-Element an, <xref:System.Windows.Documents.Run> während das zweite nicht. Beide Absätze generieren eine identische Ausgabe.

[!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]

> [!NOTE]
> Beginnend mit dem .NET Framework 4 ist die- <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft des- <xref:System.Windows.Documents.Run> Objekts eine Abhängigkeits Eigenschaft. Sie können die <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft an eine Datenquelle binden, z. b <xref:System.Windows.Controls.TextBlock> . an. Die- <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft unterstützt vollständig eine unidirektionale Bindung. Die-Eigenschaft unterstützt auch die bidirektionale <xref:System.Windows.Documents.Run.Text%2A> Bindung, mit Ausnahme von <xref:System.Windows.Controls.RichTextBox> . Ein Beispiel finden Sie unter <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.

**Spanne**

<xref:System.Windows.Documents.Span>gruppiert andere Inline Inhaltselemente. Ein inhärentes Rendering wird nicht auf den Inhalt in einem- <xref:System.Windows.Documents.Span> Element angewendet. Elemente, die von Erben <xref:System.Windows.Documents.Span> , einschließlich <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Documents.Bold> <xref:System.Windows.Documents.Italic> und, <xref:System.Windows.Documents.Underline> wenden Formatierungen auf Text an.

Im folgenden finden Sie ein Beispiel für eine <xref:System.Windows.Documents.Span> , die verwendet wird, um Inline Inhalte einschließlich Text, ein <xref:System.Windows.Documents.Bold> -Element und ein-Element zu enthalten <xref:System.Windows.Controls.Button> .

[!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]

Der folgende Screenshot zeigt, wie dieses Beispiel gerendert wird.

![Bildschirmabbildung: Gerendertes SPAN-Beispiel](./media/flow-spanexample.gif "Flow_SpanExample")

**InlineUIContainer**

<xref:System.Windows.Documents.InlineUIContainer>ermöglicht <xref:System.Windows.UIElement> , dass Elemente (d. h. ein Steuer <xref:System.Windows.Controls.Button> Element wie) in ein <xref:System.Windows.Documents.Inline> Inhalts Element eingebettet werden. Dieses Element ist das Inline Äquivalent zu den <xref:System.Windows.Documents.BlockUIContainer> oben beschriebenen. Im folgenden finden Sie ein Beispiel, in dem verwendet wird <xref:System.Windows.Documents.InlineUIContainer> , um ein <xref:System.Windows.Controls.Button> Inline in eine einzufügen <xref:System.Windows.Documents.Paragraph> .

[!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.InlineUIContainer>muss nicht explizit im Markup verwendet werden. Wenn Sie sie weglassen, <xref:System.Windows.Documents.InlineUIContainer> wird bei der Kompilierung des Codes trotzdem ein erstellt.

**Figure und Floater**

<xref:System.Windows.Documents.Figure>und <xref:System.Windows.Documents.Floater> dienen zum Einbetten von Inhalten in Fluss Dokumenten mit Platzierungs Eigenschaften, die unabhängig vom primären Inhalts Fluss angepasst werden können. <xref:System.Windows.Documents.Figure>-oder- <xref:System.Windows.Documents.Floater> Elemente werden häufig verwendet, um Inhalts Teile hervorzuheben oder hervorzuheben, um unterstützende Bilder oder andere Inhalte innerhalb des Hauptinhalts Flusses zu hosten oder um lose verwandte Inhalte wie Ankündigungen einzufügen.

Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Documents.Figure> in einen Text Absatz eingebettet wird.

[!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]

Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.

![Bildschirmabbildung: Abbildungsbeispiel](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")

<xref:System.Windows.Documents.Figure>und <xref:System.Windows.Documents.Floater> unterscheiden sich auf verschiedene Weise und werden für verschiedene Szenarien verwendet.

**Abbildung:**

- Kann positioniert werden: Sie können die horizontalen und vertikalen Textmarken so festlegen, dass diese relativ an der Seite, dem Inhalt, der Spalte oder dem Absatz andocken. Sie können auch die <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> Eigenschaften und verwenden <xref:System.Windows.Documents.Figure.VerticalOffset%2A> , um beliebige Offsets anzugeben.

- Kann für mehr als eine Spalte festgelegt werden: Sie können <xref:System.Windows.Documents.Figure> Height und Width auf Vielfache von Seiten-, Inhalts-oder Spalten Höhe oder-Breite festlegen. Beachten Sie, dass im Fall von Seiten und Inhalt keine Vielfachen über 1 zulässig sind. Beispielsweise können Sie die Breite eines <xref:System.Windows.Documents.Figure> auf "0,5 page" oder "0,25 Content" oder "2 Column" festlegen. Sie können die Höhe und Breite auch auf absolute Pixelwerte festlegen.

- Wird nicht paginiert: Wenn der Inhalt in einem <xref:System.Windows.Documents.Figure> nicht in den passt <xref:System.Windows.Documents.Figure> , wird der Inhalt, der passend ist, und der verbleibende Inhalt geht verloren.

**Floater:**

- Kann nicht positioniert werden und wird gerendert, wo Speicherplatz dafür verfügbar gemacht werden kann. Sie können den Offset nicht festlegen oder einen verankern <xref:System.Windows.Documents.Floater> .

- Kann nicht auf mehr als eine Spalte skaliert werden: standardmäßig <xref:System.Windows.Documents.Floater> in einer Spalte. Sie verfügt über eine- <xref:System.Windows.Documents.Floater.Width%2A> Eigenschaft, die auf einen absoluten Pixelwert festgelegt werden kann. Wenn dieser Wert jedoch größer als eine Spaltenbreite ist, wird er ignoriert, und der Floater wird in einer Spalte formatiert. Sie können die Größe auf weniger als eine Spalte festlegen, indem Sie die richtige Pixel Breite festlegen, aber die Größe ist nicht Spalten bezogen, sodass "0,5 Column" kein gültiger Ausdruck für die <xref:System.Windows.Documents.Floater> Breite ist. <xref:System.Windows.Documents.Floater>hat keine Height-Eigenschaft, und die Höhe kann nicht festgelegt werden. die Höhe hängt vom Inhalt ab.

- <xref:System.Windows.Documents.Floater>paginiert: wenn sein Inhalt mit der angegebenen Breite auf mehr als eine Spalten Höhe erweitert wird, unterbricht Floater und paginiert die nächste Spalte, die nächste Seite usw.

 <xref:System.Windows.Documents.Figure>ist ein guter Ort, um eigenständigen Inhalt zu platzieren, in dem Sie die Größe und Positionierung steuern möchten, und Sie sind sicher, dass der Inhalt in die angegebene Größe passt. <xref:System.Windows.Documents.Floater>ist ein guter Ausgangspunkt, um mehr frei fließenden Inhalt zu platzieren, der dem Inhalt der Hauptseite ähnlich ist, aber von ihm getrennt ist.

**LineBreak**

<xref:System.Windows.Documents.LineBreak>bewirkt, dass ein Zeilenumbruch im fortlaufenden Inhalt auftritt. Das folgende Beispiel veranschaulicht die Verwendung von <xref:System.Windows.Documents.LineBreak>.

[!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]

Der folgende Screenshot zeigt, wie dieses Beispiel gerendert wird.

![Bildschirmabbildung: LineBreak-Beispiel](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")

### <a name="flow-collection-elements"></a>Flussauflistungselemente

In vielen der obigen Beispiele <xref:System.Windows.Documents.BlockCollection> <xref:System.Windows.Documents.InlineCollection> werden und zum programmgesteuerten Erstellen von fortlaufendem Inhalt verwendet. Wenn Sie z. b. einer Elemente hinzufügen möchten <xref:System.Windows.Documents.Paragraph> , können Sie die folgende Syntax verwenden:

```csharp
myParagraph.Inlines.Add(new Run("Some text"));
```

Dadurch wird eine <xref:System.Windows.Documents.Run> zum hinzugefügt <xref:System.Windows.Documents.InlineCollection> <xref:System.Windows.Documents.Paragraph> .  Dies entspricht dem impliziten, das <xref:System.Windows.Documents.Run> <xref:System.Windows.Documents.Paragraph> in einem in Markup gefunden wurde:

```xml
<Paragraph>
Some Text
</Paragraph>
```

Im <xref:System.Windows.Documents.BlockCollection> folgenden Beispiel wird ein neues erstellt <xref:System.Windows.Documents.Section> und dann mit der **Add** -Methode dem Inhalt eine neue hinzugefügt <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Section> .

[!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
[!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]

Neben dem Hinzufügen von Elementen zu einer Flussauflistung können Sie auch Elemente entfernen.  Im folgenden Beispiel wird das letzte- <xref:System.Windows.Documents.Inline> Element in gelöscht <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
[!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]

Im folgenden Beispiel wird der gesamte Inhalt (- <xref:System.Windows.Documents.Inline> Elemente) aus dem gelöscht <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
[!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]

Beim programmgesteuerten Arbeiten mit fortlaufendem Inhalt werden Sie diese Auflistungen wahrscheinlich häufig verwenden.

Ob ein Flow-Element ein <xref:System.Windows.Documents.InlineCollection> (Inline) oder <xref:System.Windows.Documents.BlockCollection> (Blocks) verwendet, um seine untergeordneten Elemente zu enthalten, hängt davon ab, welcher Typ von untergeordneten Elementen ( <xref:System.Windows.Documents.Block> oder <xref:System.Windows.Documents.Inline> ) in der übergeordneten Elements enthalten sein kann. Einschlussregeln für Flussinhaltselemente sind im Inhaltsschema im nächsten Abschnitt zusammengefasst.

> [!NOTE]
> Es gibt einen dritten Sammlungstyp, der mit dem fortlaufenden Inhalt verwendet wird, <xref:System.Windows.Documents.ListItemCollection> aber diese Auflistung wird nur mit verwendet <xref:System.Windows.Documents.List> . Außerdem gibt es mehrere Sammlungen, die mit verwendet werden <xref:System.Windows.Documents.Table> . Weitere Informationen finden Sie unter [Tabellen Übersicht](table-overview.md) .

<a name="content_schema"></a>

## <a name="content-schema"></a>Inhaltsschema

In Anbetracht der Anzahl verschiedener Flussinhaltselemente kann es überwältigend sein, den Überblick darüber zu behalten, welchen Typ von untergeordnetem Element ein Element einschließen kann. Das folgende Diagramm fasst die Einschlussregeln für Inhaltselemente zusammen. Die Pfeile stellen die möglichen Übergeordnet/Untergeordnet-Beziehungen dar.

![Diagramm: Flussinhalt-Kapselungsschema](./media/flow-content-schema.png "Flow_Content_Schema")

Wie aus dem obigen Diagramm ersichtlich ist, werden die untergeordneten Elemente, die für ein Element zulässig sind, nicht notwendigerweise bestimmt, ob es sich um ein- <xref:System.Windows.Documents.Block> Element oder ein- <xref:System.Windows.Documents.Inline> Element handelt. Beispielsweise kann ein- <xref:System.Windows.Documents.Span> Element (ein- <xref:System.Windows.Documents.Inline> Element) nur untergeordnete Elemente aufweisen, <xref:System.Windows.Documents.Inline> während ein <xref:System.Windows.Documents.Figure> (auch ein- <xref:System.Windows.Documents.Inline> Element) nur untergeordnete Elemente aufweisen kann <xref:System.Windows.Documents.Block> . Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Als Beispiel verwenden wir das Diagramm, um zu bestimmen, wie der fortlaufende Inhalt eines erstellt wird <xref:System.Windows.Controls.RichTextBox> .

**1.** ein <xref:System.Windows.Controls.RichTextBox> muss einen enthalten <xref:System.Windows.Documents.FlowDocument> , der wiederum ein von <xref:System.Windows.Documents.Block> abgeleitetes Objekt enthalten muss. Im Folgenden finden Sie das entsprechende Segment aus dem Diagramm oben.

![Diagramm: RichTextBox-Kapselungsregeln](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")

Bis jetzt könnte das Markup wie folgt aussehen.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]

**2.** gemäß dem Diagramm gibt es mehrere Elemente, <xref:System.Windows.Documents.Block> aus denen Sie auswählen können <xref:System.Windows.Documents.Paragraph> ,,, <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.List> und <xref:System.Windows.Documents.BlockUIContainer> (siehe von Block abgeleitete Klassen oben). Nehmen wir an, wir möchten ein <xref:System.Windows.Documents.Table> . Gemäß dem obigen Diagramm enthält eine eine <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.TableRowGroup> enthaltende <xref:System.Windows.Documents.TableRow> Elemente, die Elemente enthalten, <xref:System.Windows.Documents.TableCell> die ein von <xref:System.Windows.Documents.Block> abgeleitetes Objekt enthalten. Im folgenden finden Sie das entsprechende Segment, das <xref:System.Windows.Documents.Table> aus dem obigen Diagramm entnommen wurde.

![Diagramm: übergeordnetes&#47;untergeordnetes Schema für Tabelle](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")

Im Folgenden finden Sie das entsprechende Markup.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]

**3.** ein oder mehrere- <xref:System.Windows.Documents.Block> Elemente sind unterhalb von erforderlich. <xref:System.Windows.Documents.TableCell> Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Dies ist mit einem- <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Run> Element möglich. Im folgenden finden Sie die entsprechenden Segmente aus dem Diagramm, die zeigen, dass ein <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Inline> -Element akzeptiert und ein <xref:System.Windows.Documents.Run> (ein- <xref:System.Windows.Documents.Inline> Element) nur nur-Text annehmen kann.

![Diagramm: übergeordnetes&#47;untergeordnetes Schema für Absatz](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")

![Diagramm: übergeordnetes&#47;untergeordnetes Schema für die Testlauf](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")

Nachstehend finden Sie das gesamte Beispiel im Markup.

[!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]

<a name="customizing_text"></a>

## <a name="customizing-text"></a>Anpassen von Text

In der Regel ist Text der am weitesten verbreitete Inhaltstyp in einem Flussdokument. Obwohl die oben eingeführten Objekte verwendet werden können, um die meisten Aspekte beim Rendern von Text zu steuern, gibt es einige andere Methoden zum Anpassen von Text, die in diesem Abschnitt abgedeckt werden.

### <a name="text-decorations"></a>Textverzierungen

Textverzierungen ermöglichen es Ihnen, die Effekte „Unterstreichen“, „Überstreichen“, „Grundlinie“ und „Durchgestrichen“ auf den Text anzuwenden (siehe Bilder unten). Diese Dekorationen werden mithilfe der- <xref:System.Windows.Documents.Inline.TextDecorations%2A> Eigenschaft hinzugefügt, die durch eine Reihe von-Objekten verfügbar gemacht wird, einschließlich <xref:System.Windows.Documents.Inline> , <xref:System.Windows.Documents.Paragraph> , <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.TextBox> .

Das folgende Beispiel veranschaulicht das Festlegen der <xref:System.Windows.Documents.Paragraph.TextDecorations%2A>-Eigenschaft einer <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]

[!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
[!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]

Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.

![Bildschirmabbildung: Text mit standardmäßigem Durchstreicheffekt](./media/inline-textdec-strike.png "Inline_TextDec_Strike")

Die folgenden Abbildungen zeigen, wie die über-, **Baseline**-und unter **Strich** -Dekorationen **dargestellt**werden.

![Bildschirmabbildung: Überstrich-TextDecorator](./media/inline-textdec-over.png "Inline_TextDec_Over")

![Bildschirmabbildung: Standardmäßiger Baseline-Effekt auf Text](./media/inline-textdec-base.png "Inline_TextDec_Base")

![Bildschirmabbildung: Text mit standardmäßigem Unterstreichungseffekt](./media/inline-textdec-under.png "Inline_TextDec_Under")

### <a name="typography"></a>Typografie

Die- <xref:System.Windows.Documents.TextElement.Typography%2A> Eigenschaft wird von den meisten Fluss bezogenen Inhalten <xref:System.Windows.Documents.TextElement> , einschließlich, <xref:System.Windows.Documents.FlowDocument> , <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.TextBox> , verfügbar gemacht. Diese Eigenschaft wird verwendet, um typografische Eigenschaften/Variationen von Text (d.h. Kapitälchen oder Großbuchstaben, hoch- und tiefgestellter Text usw.) zu steuern.

Im folgenden Beispiel wird gezeigt, wie das- <xref:System.Windows.Documents.TextElement.Typography%2A> Attribut mithilfe von <xref:System.Windows.Documents.Paragraph> als Beispiel Element festgelegt wird.

[!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]

Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.

![Bildschirmabbildung: Text mit geänderter Typografie](./media/textelement-typog.png "TextElement_Typog")

Im Gegensatz dazu zeigt die folgende Abbildung, wie ein ähnliches Beispiel mit typografischen Standardeigenschaften gerendert wird.

![Bildschirmabbildung: Text mit geänderter Typografie](./media/textelement-typog-default.png "TextElement_Typog_Default")

Im folgenden Beispiel wird gezeigt, wie die-Eigenschaft Programm gesteuert festgelegt wird <xref:System.Windows.Controls.TextBox.Typography%2A> .

[!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
[!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]

Weitere Informationen zur Typografie finden Sie unter [Typografie in WPF](typography-in-wpf.md) .

## <a name="see-also"></a>Siehe auch

- [Text](optimizing-performance-text.md)
- [Typografie in WPF](typography-in-wpf.md)
- [Artikel zu Vorgehensweisen](flow-content-elements-how-to-topics.md)
- [Übersicht über das TextElement-Inhaltsmodell](textelement-content-model-overview.md)
- [Übersicht über RichTextBox](../controls/richtextbox-overview.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Tabellen Übersicht](table-overview.md)
- [Übersicht über Anmerkungen](annotations-overview.md)
