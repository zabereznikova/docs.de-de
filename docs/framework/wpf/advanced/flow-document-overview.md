---
title: Übersicht über Flussdokumente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: 14402bde39ec90d8ef17ed5ee07f9eefb8151939
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139606"
---
# <a name="flow-document-overview"></a>Übersicht über Flussdokumente
Flussdokumente dienen der Optimierung der Anzeige und Lesbarkeit. Statt auf ein vordefiniertes Layout festgelegt zu werden, passen Flussdokumente ihren Inhalt basierend auf Laufzeitvariablen dynamisch an Variablen wie Fenstergröße, Geräteauflösung und optionale Benutzereinstellungen an und brechen den Inhalt dynamisch um. Zudem bieten Flussdokumente erweiterte Dokumentfunktionen, z.B. Paginierung und Spalten. Dieses Thema enthält eine Übersicht über Flussdokumente und deren Erstellung.  

<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Was ist ein Flussdokument?  
 Ein Flussdokument wurde konzipiert, um abhängig von der Fenstergröße, der Geräteauflösung und anderen Umgebungsvariablen den „Inhalt dynamisch umzubrechen“. Zudem verfügen Flussdokumente über eine Vielzahl integrierter Funktionen, inklusive der Suche, Anzeigemodi zur Optimierung der Lesbarkeit und der Möglichkeit zum Ändern der Größe und Darstellung von Schriftarten. Flussdokumente werden am besten verwendet, wenn das erleichterte Lesen das Hauptgebrauchsszenario des Dokuments darstellt. Im Gegensatz dazu sind fixierte Dokumente für eine statische Darstellung entworfen. Fixierte Dokumente sind hilfreich, wenn die Originaltreue des Quellinhalts wichtig ist. Finden Sie unter [Dokumente in WPF](documents-in-wpf.md) für Weitere Informationen zu verschiedenen Arten von Dokumenten.  
  
 Die folgende Abbildung zeigt ein Beispielflussdokument in mehreren Fenstern von verschiedener Größe. Wenn sich der Bildschirmbereich ändert, bricht der Inhalt dynamisch um, um den verfügbaren Platz bestmöglich auszunutzen.  
  
 ![Flussdokumentinhalt dynamisch umgebrochen](./media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Wie in dem Bild oben dargestellt, kann fortlaufender Inhalt viele Komponenten umfassen, einschließlich Absätzen, Listen, Bilder usw. Diese Komponenten entsprechen Elementen im Markup und Objekten in prozeduralem Code. Wir werden diese Klassen werden im Detail weiter unten in der [Flussbezogene Klassen](#flow_related_classes) Abschnitt dieser Übersicht. Jetzt müssen Sie hier ein einfaches Codebeispiel, das ein Flussdokument bestehend aus einem Absatz mit fett formatiertem Text und eine Liste erstellt wird.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieser Codeausschnitt aussieht.  
  
 ![Screenshot: Gerendertes FlowDocument-Beispiel](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 In diesem Beispiel die <xref:System.Windows.Controls.FlowDocumentReader> Steuerelement wird zum Hosten des fortlaufenden Inhalts verwendet. Finden Sie unter [Flussdokumenttypen](#flow_document_types) Weitere Informationen zum Hosten von Steuerelementen von fortlaufendem Inhalt. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, und <xref:System.Windows.Documents.Bold> Elemente dienen zum Steuern der inhaltsformatierung basierend auf ihrer Reihenfolge im Markup. Z. B. die <xref:System.Windows.Documents.Bold> Element erstreckt sich auf nur einen Teil des Texts im Absatz; daher nur dieser Teil der Text fett formatiert ist. Wenn Sie HTML verwendet haben, wird Ihnen dies vertraut sein.  
  
 Wie in der obigen Abbildung verdeutlicht es gibt mehrere Funktionen in Flussdokumenten integriert:
  
-   Suchen: Ermöglicht dem Benutzer um eine Volltextsuche ein ganzes Dokument auszuführen.  
  
-   Anzeigemodus: Der Benutzer kann seinen bevorzugten Anzeigemodus, einschließlich einen Single-Page (Seite-an-a-Time)-Anzeigemodus, eine zwei-Seite-an-a-Time (Buch lesen Format) anzeigen, Modus und einen fortlaufenden Bildlaufmodus anzeigen (buchleseformat) von auswählen.  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Steuerelemente für die Seitennavigation: Wenn der Anzeigemodus des Dokuments Seiten verwendet werden, enthalten die Steuerelemente für die Seitennavigation eine Schaltfläche zum Wechseln der nächsten Seite (Pfeil nach unten) oder vorherige Seite (Pfeil), als auch Indikatoren für die aktuelle Seitenzahl und die Gesamtzahl der Seiten. Das Blättern durch Seiten funktioniert auch mithilfe der Pfeiltasten auf der Tastatur.  
  
-   Zoom: Die Zoomsteuerelemente ermöglichen erhöhen oder verringern die Zoomstufe, indem Sie auf das Pluszeichen oder minusschaltfächen klickt den Benutzer bzw. aus. Die Zoomsteuerelemente umfassen zudem einen Schieberegler zum Anpassen der Zoomstufe. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Diese Funktionen können basierend auf dem zum Hosten des fortlaufenden Inhalts verwendeten Steuerelement bearbeitet werden. Im nächsten Abschnitt werden die verschiedenen Steuerelemente beschrieben.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Flussdokumenttypen  
 Die Anzeige und Darstellung von Flussdokumentinhalt hängt davon ab, welches Objekt zum Hosten des fortlaufenden Inhalts verwendet wird. Es gibt vier Steuerelemente, die die Anzeige von fortlaufendem Inhalt zu unterstützen: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Diese Steuerelemente werden nachstehend kurz beschrieben.  
  
 **Hinweis:** <xref:System.Windows.Documents.FlowDocument> ist erforderlich, um direkt Host fließendem Inhalt, also alle diese Anzeigesteuerelemente eine <xref:System.Windows.Documents.FlowDocument> zum Hosten von fortlaufendem Inhalt zu aktivieren.
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> enthält Features, mit die den Benutzer dynamisch zwischen verschiedenen Anzeigemodi, einschließlich einen Single-Page (Seite-an-a-Time)-Anzeigemodus, eine zwei-Seite-an-a-Time (Buch lesen Format) anzeigen, Modus und einen fortlaufenden Bildlaufmodus anzeigen (buchleseformat) von auswählen können. Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Wenn Sie nicht die Fähigkeit zum dynamischen Wechsel zwischen verschiedenen Anzeigemodi benötigen <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> bieten schlankere Flow Content-Viewer, die in einem bestimmten Anzeigemodus behoben werden.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Zeigt den Inhalt im Seite-an-a-Time Anzeigemodus, while <xref:System.Windows.Controls.FlowDocumentScrollViewer> zeigt den Inhalt im fortlaufenden Bildlaufmodus. Beide <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> wurden korrigiert, um einen bestimmten Anzeigemodus festgelegt. Vergleichen mit <xref:System.Windows.Controls.FlowDocumentReader>, darunter Features, die der Benutzer dynamisch zwischen verschiedenen Anzeigemodi wählen können (gemäß der <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> Enumeration), dabei jedoch weitere ressourcenintensiv als <xref:System.Windows.Controls.FlowDocumentPageViewer> oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Eine vertikale Scrollleiste wird standardmäßig immer angezeigt, eine horizontale Scrollleiste nur nach Bedarf. Der Standard-Benutzeroberfläche für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste, aber die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> Eigenschaft kann verwendet werden, um eine integrierte Symbolleiste aktiviert.  
  
### <a name="richtextbox"></a>RichTextBox  
 Sie verwenden eine <xref:System.Windows.Controls.RichTextBox> sollen dem Benutzer ermöglichen, fortlaufenden Inhalt zu bearbeiten. Z. B. Wenn Sie einen Editor erstellen, die einen Benutzer zum Bearbeiten von Dinge wie Tabellen, kursiv und fett formatieren, usw., verwenden Sie eine <xref:System.Windows.Controls.RichTextBox>. Finden Sie unter [Übersicht über RichTextBox](../controls/richtextbox-overview.md) für Weitere Informationen.  
  
 **Hinweis**: Fortlaufender Inhalt in einem <xref:System.Windows.Controls.RichTextBox> verhält sich nicht genau wie fortlaufender Inhalt innerhalb anderer Steuerelemente. Beispielsweise gibt es sind keine Spalten in einer <xref:System.Windows.Controls.RichTextBox> und daher kein automatisches Größenänderungsverhalten. Darüber hinaus sind die typischen integrierten Funktionen von fortlaufendem Inhalt wie Suche, Anzeigemodus, Modus, Seitennavigation und Zoom nicht verfügbar innerhalb einer <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Erstellen von fortlaufendem Inhalt  
 Fortlaufendem Inhalt kann komplex sein, bestehend aus verschiedenen Elementen einschließlich Text, Bilder, Tabellen, und sogar <xref:System.Windows.UIElement> abgeleiteten Klassen wie Steuerelemente. Um zu verstehen, wie komplexer fortlaufender Inhalt erstellt wird, sind die folgenden Punkte wichtig:  
  
-   **Flussbezogene Klassen**: Jede in fortlaufendem Inhalt verwendete Klasse verfügt über einen bestimmten Zweck. Darüber hinaus hilft Ihnen die hierarchische Beziehung zwischen Flussklassen dabei, zu verstehen, wie sie verwendet werden. Z. B. von abgeleiteten Klassen der <xref:System.Windows.Documents.Block> -Klasse verwendet, um andere Objekte enthalten, während die abgeleitete Klassen <xref:System.Windows.Documents.Inline> enthält Objekte, die angezeigt werden.  
  
-   **Inhaltsschema**: Ein Flussdokument kann eine große Anzahl von geschachtelten Elementen erfordern. Das Inhaltsschema gibt mögliche Übergeordnet/Untergeordnet-Beziehungen zwischen Elementen an.  
  
 In den folgenden Abschnitten wird jeder dieser Bereiche ausführlicher erklärt.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Flussbezogene Klassen  
 Das folgende Diagramm zeigt die am häufigsten bei fortlaufendem Inhalt verwendeten Objekte:  
  
 ![Diagramm: Flow-Klassenhierarchie](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 Für die Zwecke des fortlaufenden Inhalts gibt es zwei wichtige Kategorien:  
  
1.  **Blockabgeleitete Klassen**: Auch "Blockinhaltselemente" oder einfach "Blockelemente" genannt. Elemente, die von erben <xref:System.Windows.Documents.Block> kann verwendet werden, um Elemente unter einem gemeinsamen übergeordneten Element gruppiert oder gemeinsame Attribute auf eine Gruppe angewendet.  
  
2.  **Inlineabgeleitete Klassen**: Auch "Inlineinhaltselemente" oder einfach "Inlineelemente" genannt. Elemente, die von erben <xref:System.Windows.Documents.Inline> entweder in einem Blockelement oder einem anderen Inlineelement enthalten sind. Inlineelemente werden oft als direkter Container für Inhalt verwendet, der auf dem Bildschirm gerendert wird. Z. B. eine <xref:System.Windows.Documents.Paragraph> (Block-Element) darf eine <xref:System.Windows.Documents.Run> (Inline-Element), aber die <xref:System.Windows.Documents.Run> enthält den Text, der auf dem Bildschirm gerendert wird.  
  
 Jede Klasse in diesen zwei Kategorien wird nachstehend kurz beschrieben.  
  
### <a name="block-derived-classes"></a>Blockabgeleitete Klassen  
 **Absatz**  
  
 <xref:System.Windows.Documents.Paragraph> wird normalerweise zum Gruppieren von Inhalten in einem Absatz verwendet. Die einfachste und häufigste Verwendung von Paragraph ist, einen Textabsatz zu erstellen.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Sie können jedoch auch andere inlineabgeleitete Elemente enthalten, wie unten dargestellt wird. 
  
 **Abschnitt**  
  
 <xref:System.Windows.Documents.Section> wird nur verwendet, um andere enthält <xref:System.Windows.Documents.Block>-abgeleitete Elemente. Sie wendet keine Standardformatierungen auf die Elemente an, die sie einschließt. Allerdings alle Standardwerte für die Eigenschaft Gruppe auf einen <xref:System.Windows.Documents.Section> gilt für die untergeordneten Elemente. Eine Section-Klasse ermöglicht es Ihnen auch, ihre untergeordnete Auflistung programmgesteuert zu durchlaufen. <xref:System.Windows.Documents.Section> werden in ähnlicher Weise wie für die \<DIV >-Tag in HTML.  
  
 Im folgenden Beispiel werden drei Absätze unter einem definierten <xref:System.Windows.Documents.Section>. Der Abschnitt enthält eine <xref:System.Windows.Documents.TextElement.Background%2A> Eigenschaftswert von Rot, daher ist die Hintergrundfarbe des Absatzes Rot ist.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer> ermöglicht <xref:System.Windows.UIElement> Elemente (d. h. eine <xref:System.Windows.Controls.Button>) in blockabgeleiteten fortlaufenden Inhalt eingebettet werden. <xref:System.Windows.Documents.InlineUIContainer> (siehe unten) wird zum Einbetten von <xref:System.Windows.UIElement> -Elemente in inlineabgeleiteten fortlaufenden Inhalt. <xref:System.Windows.Documents.BlockUIContainer> und <xref:System.Windows.Documents.InlineUIContainer> sind wichtig, da es keine andere Möglichkeit zum Verwenden gibt einer <xref:System.Windows.UIElement> in fortlaufendem Inhalt, es sei denn, es in einem der beiden Elemente enthalten ist.  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Documents.BlockUIContainer> Element Host <xref:System.Windows.UIElement> Objekte innerhalb von fortlaufendem Inhalt.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird:  
  
 ![Screenshot mit einem UIElement eingebettet in fortlaufenden Inhalt.](./media/flow-document-overview/embedded-blockuicontainer.png)  
  
 **Liste**  
  
 <xref:System.Windows.Documents.List> wird verwendet, um eine Liste mit Aufzählungszeichen oder Zahlen erstellen. Legen Sie die <xref:System.Windows.Documents.List.MarkerStyle%2A> Eigenschaft, um eine <xref:System.Windows.TextMarkerStyle> Enumerationswert, der den Stil der Liste zu bestimmen. Das folgende Beispiel zeigt, wie Sie eine einfache Liste erstellen.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Hinweis:** <xref:System.Windows.Documents.List> ist das einzige Flusselement, das verwendet die <xref:System.Windows.Documents.ListItemCollection> zum Verwalten von untergeordneten Elementen.  
  
 **Tabelle**  
  
 <xref:System.Windows.Documents.Table> Dient zum Erstellen einer Tabelle. <xref:System.Windows.Documents.Table> ähnelt der <xref:System.Windows.Controls.Grid> -Element, aber es weist mehr Funktionen und erfordert daher höheren Ressourcenaufwand. Da <xref:System.Windows.Controls.Grid> ist eine <xref:System.Windows.UIElement>, es kann nicht in fortlaufendem Inhalt verwendet werden, es sei denn, sie in enthalten ist ein <xref:System.Windows.Documents.BlockUIContainer> oder <xref:System.Windows.Documents.InlineUIContainer>. Weitere Informationen zu <xref:System.Windows.Documents.Table>, finden Sie unter [Tabellenübersicht](table-overview.md).  
  
### <a name="inline-derived-classes"></a>Inlineabgeleitete Klassen  
 **Run**  
  
 <xref:System.Windows.Documents.Run> wird verwendet, um unformatierten Text einzuschließen. Sie erwarten wahrscheinlich <xref:System.Windows.Documents.Run> Objekte, die häufig in verwendet werden, fortlaufende Inhalte. Allerdings im Markup <xref:System.Windows.Documents.Run> Elemente sind nicht erforderlich, um explizit verwendet werden. <xref:System.Windows.Documents.Run> ist erforderlich, um Sie beim Erstellen oder Bearbeiten von Flussdokumenten mithilfe von Code verwendet werden. Zum Beispiel im Markup unterhalb des ersten <xref:System.Windows.Documents.Paragraph> gibt an, die <xref:System.Windows.Documents.Run> -Element explizit während der zweite jedoch nicht. Beide Absätze generieren eine identische Ausgabe.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Hinweis**:  Ab der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft der <xref:System.Windows.Documents.Run> Objekt ist eine Abhängigkeitseigenschaft. Sie binden die <xref:System.Windows.Documents.Run.Text%2A> -Eigenschaft an eine Datenquelle, beispielsweise eine <xref:System.Windows.Controls.TextBlock>. Die <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft unterstützt die unidirektionale Bindung. Die <xref:System.Windows.Documents.Run.Text%2A> Eigenschaft unterstützt auch die bidirektionale Bindung, mit Ausnahme von <xref:System.Windows.Controls.RichTextBox>. Ein Beispiel finden Sie unter <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> gruppiert andere Inlineinhaltselemente. Kein inhärentes Rendering angewendet wird, um Inhalte in einem <xref:System.Windows.Documents.Span> Element. Allerdings Elemente, die von erben <xref:System.Windows.Documents.Span> einschließlich <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> und <xref:System.Windows.Documents.Underline> gelten Text formatieren.  
  
 Im folgenden finden Sie ein Beispiel für eine <xref:System.Windows.Documents.Span> verwendet wird, um Inlineinhalt einschließlich Text, enthalten eine <xref:System.Windows.Documents.Bold> -Element, und ein <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 Der folgende Screenshot zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Gerendertes Span-Beispiel](./media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer> ermöglicht <xref:System.Windows.UIElement> Elemente (d. h. ein Steuerelement wie <xref:System.Windows.Controls.Button>) einbetten in eine <xref:System.Windows.Documents.Inline> Content-Element. Dieses Element ist die Inlineentsprechung zur <xref:System.Windows.Documents.BlockUIContainer> oben beschriebenen. Im folgenden finden Sie ein Beispiel, verwendet <xref:System.Windows.Documents.InlineUIContainer> zum Einfügen einer <xref:System.Windows.Controls.Button> Inline in einer <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Hinweis:** <xref:System.Windows.Documents.InlineUIContainer> muss nicht explizit im Markup verwendet werden. Wenn Sie ihn weglassen ein <xref:System.Windows.Documents.InlineUIContainer> wird trotzdem erstellt werden, wenn der Code kompiliert wird.  
  
 **Figure und Floater**  
  
 <xref:System.Windows.Documents.Figure> und <xref:System.Windows.Documents.Floater> werden verwendet, um Inhalt in Flussdokumenten mit Positionierungseigenschaften einzubetten, die unabhängig vom fortlaufenden Primärinhalt angepasst werden können. <xref:System.Windows.Documents.Figure> oder <xref:System.Windows.Documents.Floater> Elemente sind häufig markiert oder Teile von Inhalt, um unterstützende Bilder oder anderer Inhalte innerhalb der Hauptinhalt gehostet hervorgehoben oder zum Einfügen von lose verbundener Inhalt wie Werbung.  
  
 Das folgende Beispiel zeigt, wie Sie Einbetten einer <xref:System.Windows.Documents.Figure> in einen Textabsatz.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Abbildungsbeispiel](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure> und <xref:System.Windows.Documents.Floater> unterscheiden sich auf verschiedene Weise und für verschiedene Szenarios verwendet werden.  
  
 **Abbildung:**  
  
-   Kann positioniert werden: Sie können die horizontalen und vertikalen Textmarken auf es Bezug auf die Seite, die Inhalte, die Spalte oder die Absatz andocken festlegen. Sie können auch die <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> und <xref:System.Windows.Documents.Figure.VerticalOffset%2A> Eigenschaft, um beliebige Offsets anzugeben.  
  
-   Ist mehr als einer Spalte beträchtliche: Sie können festlegen, <xref:System.Windows.Documents.Figure> Höhe und Breite auf ein Vielfaches von Seite, Inhalt oder Spalte Höhe oder Breite. Beachten Sie, dass im Fall von Seiten und Inhalt keine Vielfachen über 1 zulässig sind. Sie können z. B. die Breite des Festlegen einer <xref:System.Windows.Documents.Figure> "0.5 Page" oder "0.25 Content" oder "2 Column" sein. Sie können die Höhe und Breite auch auf absolute Pixelwerte festlegen.  
  
-   Paginiert nicht: Wenn der Inhalt in einem <xref:System.Windows.Documents.Figure> passt nicht in der <xref:System.Windows.Documents.Figure>, passt der Inhalt wird ausgegeben, und der restliche Inhalt geht verloren  
  
 **Floater:**  
  
-   Kann nicht positioniert werden und wird gerendert, wo Speicherplatz dafür verfügbar gemacht werden kann. Sie können nicht festgelegt, den Offset oder die Verankerung einer <xref:System.Windows.Documents.Floater>.  
  
-   Mehr als eine Spalte kann nicht festgelegt werden: In der Standardeinstellung <xref:System.Windows.Documents.Floater> Größe an eine Spalte. Es wurde eine <xref:System.Windows.Documents.Floater.Width%2A> -Eigenschaft, die festgelegt werden kann, um einen absoluten Pixelwert, aber wenn ist dieser Wert größer als eine Spaltenbreite wird ignoriert und die Floater-Klasse ist Größe einer Spalte. Sie können die Größe auf weniger als einer Spalte durch die richtige Pixelbreite festlegen, größenanpassung ist jedoch nicht spaltenabhängig, sodass "0.5Column" kein gültiger Ausdruck für ist <xref:System.Windows.Documents.Floater> Breite. <xref:System.Windows.Documents.Floater> hat keine Höheneigenschaft, und es ist Höhe kann nicht festgelegt werden, die die Höhe hängt vom Inhalt  
  
-   <xref:System.Windows.Documents.Floater> paginiert: Wenn der Inhalt bei angegebener Breite auf mehr als 1 Spaltenhöhe erweitert wird, bricht Floater um und paginiert zur nächsten Spalte, nächsten Seite usw.  
  
 <xref:System.Windows.Documents.Figure> ist ein guter Ausgangspunkt zum eigenständigen Inhalt zu platzieren, in denen Sie zum Steuern der Größe möchten, und Positionierung und sind davon überzeugt, dass der Inhalt in die angegebene Größe passt. <xref:System.Windows.Documents.Floater> ist ein guter Ausgangspunkt, um weitere kostenlose Inhalt zu platzieren, die ähnlich wie der Inhalt der Hauptseite fließen, aber von diesem getrennt ist.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> bewirkt, dass einen Zeilenumbruch in fortlaufendem Inhalt. Das folgende Beispiel veranschaulicht die Verwendung von <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 Der folgende Screenshot zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: LineBreak-Beispiel](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Flussauflistungselemente  
 In vielen der oben genannten Beispiele die <xref:System.Windows.Documents.BlockCollection> und <xref:System.Windows.Documents.InlineCollection> werden verwendet, um fortlaufenden Inhalt programmgesteuert zu erstellen. Um beispielsweise zum Hinzufügen von Elementen einer <xref:System.Windows.Documents.Paragraph>, können Sie die Syntax verwenden:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Dadurch wird eine <xref:System.Windows.Documents.Run> auf die <xref:System.Windows.Documents.InlineCollection> von der <xref:System.Windows.Documents.Paragraph>.  Dies ist identisch mit der impliziten <xref:System.Windows.Documents.Run> finden Sie in einem <xref:System.Windows.Documents.Paragraph> im Markup:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Als Beispiel zeigt die Verwendung der <xref:System.Windows.Documents.BlockCollection>, das folgende Beispiel erstellt ein neues <xref:System.Windows.Documents.Section> und verwendet dann die **hinzufügen** Methode zum Hinzufügen einer neuen <xref:System.Windows.Documents.Paragraph> auf die <xref:System.Windows.Documents.Section> Inhalt.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Neben dem Hinzufügen von Elementen zu einer Flussauflistung können Sie auch Elemente entfernen.  Das folgende Beispiel löscht das letzte <xref:System.Windows.Documents.Inline> Element in der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Das folgende Beispiel löscht den Inhalt (<xref:System.Windows.Documents.Inline> Elemente) aus der <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Beim programmgesteuerten Arbeiten mit fortlaufendem Inhalt werden Sie diese Auflistungen wahrscheinlich häufig verwenden.  
  
 Gibt an, ob ein Element für fortlaufenden verwendet eine <xref:System.Windows.Documents.InlineCollection> (Inlines) oder <xref:System.Windows.Documents.BlockCollection> (Blöcke), enthält seine untergeordneten Elemente hängt vom Typ der untergeordneten Elemente (<xref:System.Windows.Documents.Block> oder <xref:System.Windows.Documents.Inline>) kann vom übergeordneten Element enthalten sein. Einschlussregeln für Flussinhaltselemente sind im Inhaltsschema im nächsten Abschnitt zusammengefasst.  
  
 **Hinweis**: Es wird ein dritter Typ der Auflistung, die mit fortlaufendem Inhalt, verwendet der <xref:System.Windows.Documents.ListItemCollection>, aber diese Auflistung wird nur verwendet, mit einer <xref:System.Windows.Documents.List>. Darüber hinaus werden mehrere Auflistungen mit verwendet <xref:System.Windows.Documents.Table>. Finden Sie unter [Tabellenübersicht](table-overview.md) für Weitere Informationen.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Inhaltsschema  
 In Anbetracht der Anzahl verschiedener Flussinhaltselemente kann es überwältigend sein, den Überblick darüber zu behalten, welchen Typ von untergeordnetem Element ein Element einschließen kann. Das folgende Diagramm fasst die Einschlussregeln für Inhaltselemente zusammen. Die Pfeile stellen die möglichen Übergeordnet/Untergeordnet-Beziehungen dar.  
  
 ![Diagramm: Flussinhalt-einschlussschema](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Wie aus dem Diagramm oben ersichtlich ist, die für ein Element zulässigen untergeordneten Elemente werden nicht zwingend davon bestimmt, ob es sich handelt eine <xref:System.Windows.Documents.Block> Element oder ein <xref:System.Windows.Documents.Inline> Element. Z. B. eine <xref:System.Windows.Documents.Span> (ein <xref:System.Windows.Documents.Inline> Element) nur möglich, <xref:System.Windows.Documents.Inline> untergeordnete Elemente und eine <xref:System.Windows.Documents.Figure> (auch ein <xref:System.Windows.Documents.Inline> Element) nur möglich, <xref:System.Windows.Documents.Block> untergeordnete Elemente. Aus diesem Grund ist ein Diagramm nützlich, um schnell zu bestimmen, welches Element in einem anderen eingeschlossen sein kann. Als Beispiel verwenden Sie wir das Diagramm, um zu bestimmen, wie den fortlaufende Inhalt einer <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Ein <xref:System.Windows.Controls.RichTextBox> darf eine <xref:System.Windows.Documents.FlowDocument> muss wiederum eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im Folgenden finden Sie das entsprechende Segment aus dem Diagramm oben.  
  
 ![Diagramm: RichTextBox-Kapselungsregeln](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Bis jetzt könnte das Markup wie folgt aussehen.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Gemäß dem Diagramm stehen verschiedene <xref:System.Windows.Documents.Block> zu wählen, darunter Elemente <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, und <xref:System.Windows.Documents.BlockUIContainer> (Siehe blockabgeleitete Klassen, die weiter oben). Nehmen wir eine <xref:System.Windows.Documents.Table>. Gemäß dem Diagramm oben eine <xref:System.Windows.Documents.Table> enthält eine <xref:System.Windows.Documents.TableRowGroup> mit <xref:System.Windows.Documents.TableRow> Elemente, die enthalten <xref:System.Windows.Documents.TableCell> Elemente beinhalten eine <xref:System.Windows.Documents.Block>-abgeleitetes Objekt. Im folgenden finden Sie das entsprechende Segment für <xref:System.Windows.Documents.Table> stammt aus der Abbildung oben.  
  
 ![Diagramm: Übergeordnete&#47;untergeordnetes Schema für Tabelle](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 Im Folgenden finden Sie das entsprechende Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** In diesem Fall eine oder mehrere <xref:System.Windows.Documents.Block> Elemente sind erforderlich, darunter eine <xref:System.Windows.Documents.TableCell>. Um es einfach zu gestalten, fügen wir Text in die Zelle ein. Wir erreichen das mithilfe einer <xref:System.Windows.Documents.Paragraph> mit einem <xref:System.Windows.Documents.Run> Element. Im folgenden finden Sie die entsprechenden Segmente aus dem Diagramm zeigt, dass eine <xref:System.Windows.Documents.Paragraph> dauert ein <xref:System.Windows.Documents.Inline> -Element sowie eine <xref:System.Windows.Documents.Run> (ein <xref:System.Windows.Documents.Inline> Element) kann nur nur-Text annehmen.  
  
 ![Diagramm: Übergeordnete&#47;untergeordnetes Schema für Absatz](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Diagramm: Übergeordnete&#47;untergeordnetes Schema für Ausführung](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Nachstehend finden Sie das gesamte Beispiel im Markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Anpassen von Text  
 In der Regel ist Text der am weitesten verbreitete Inhaltstyp in einem Flussdokument. Obwohl die oben eingeführten Objekte verwendet werden können, um die meisten Aspekte beim Rendern von Text zu steuern, gibt es einige andere Methoden zum Anpassen von Text, die in diesem Abschnitt abgedeckt werden.  
  
### <a name="text-decorations"></a>Textverzierungen  
 Textverzierungen ermöglichen es Ihnen, die Effekte „Unterstreichen“, „Überstreichen“, „Grundlinie“ und „Durchgestrichen“ auf den Text anzuwenden (siehe Bilder unten). Diese verzierungen werden hinzugefügt, mit der <xref:System.Windows.Documents.Inline.TextDecorations%2A> -Eigenschaft, die durch eine Reihe von Objekten, einschließlich verfügbar gemacht wird <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, und <xref:System.Windows.Controls.TextBox>.  
  
 Das folgende Beispiel veranschaulicht das Festlegen der <xref:System.Windows.Documents.Paragraph.TextDecorations%2A>-Eigenschaft einer <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Text mit standardmäßigem Durchstreicheffekt](./media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Der folgenden Abbildung wird wie die **überlagernde Linie**, **Baseline**, und **Unterstreichen** Ergänzungen zu rendern, bzw.  
  
 ![Screenshot: Überstrich-TextDecorator](./media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Screenshot: Standardgrundlinieneffekt auf Text](./media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Screenshot: Text mit standardmäßigem unterstreichungseffekt](./media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Typografie  
 Die <xref:System.Windows.Documents.TextElement.Typography%2A> -Eigenschaft wird verfügbar gemacht, von den meisten flussbezogenen Inhalten einschließlich <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, und <xref:System.Windows.Controls.TextBox>. Diese Eigenschaft wird verwendet, um typografische Eigenschaften/Variationen von Text (d.h. Kapitälchen oder Großbuchstaben, hoch- und tiefgestellter Text usw.) zu steuern.  
  
 Im folgende Beispiel veranschaulicht die legen Sie die <xref:System.Windows.Documents.TextElement.Typography%2A> -Attributs unter Verwendung <xref:System.Windows.Documents.Paragraph> als Beispielelement.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Text mit geänderter Typografie](./media/textelement-typog.png "TextElement_Typog")  
  
 Im Gegensatz dazu zeigt die folgende Abbildung, wie ein ähnliches Beispiel mit typografischen Standardeigenschaften gerendert wird.  
  
 ![Screenshot: Text mit geänderter Typografie](./media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 Im folgende Beispiel veranschaulicht die legen Sie die <xref:System.Windows.Controls.TextBox.Typography%2A> Eigenschaft programmgesteuert.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Finden Sie unter [Typografie in WPF](typography-in-wpf.md) für Weitere Informationen zur Typografie.  
  
## <a name="see-also"></a>Siehe auch

- [Text](optimizing-performance-text.md)
- [Typografie in WPF](typography-in-wpf.md)
- [Gewusst wie-Themen](flow-content-elements-how-to-topics.md)
- [Übersicht über das TextElement-Inhaltsmodell](textelement-content-model-overview.md)
- [Übersicht über RichTextBox](../controls/richtextbox-overview.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über Tabellen](table-overview.md)
- [Übersicht über Anmerkungen](annotations-overview.md)
