---
title: Übersicht über Tabellen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 0888bc213be6b8037d0574bb5f9ac76e7651491a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745362"
---
# <a name="table-overview"></a>Übersicht über Tabellen
<xref:System.Windows.Documents.Table> ist ein Element auf Blockebene, die rasterbasierte Darstellung von Flussdokumentinhalten unterstützt. Die Flexibilität dieses Elements macht es nicht nur sehr hilfreich, sondern auch schwieriger zu verstehen und richtig zu verwenden.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Grundlagen zu Tabellen](#table_basics)  
  
-   [Worin unterscheidet sich eine Tabelle von einem Raster?](#table_vs_Grid)  
  
-   [Grundlegende Tabellenstruktur](#basic_table_structure)  
  
-   [Tabellenkapselung](#table_containment)  
  
-   [Zeilengruppen](#row_groupings)  
  
-   [Hintergrundrendering-Rangfolge](#rendering_precedence)  
  
-   [Überspannen von Zeilen oder Spalten](#spanning_rows_or_columns)  
  
-   [Erstellen einer Tabelle mit Code](#building_a_table_with_code)  
  
-   [Verwandte Themen] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Grundlagen zu Tabellen  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Worin unterscheidet sich eine Tabelle von einem Raster?  
 <xref:System.Windows.Documents.Table> und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, aber jede für verschiedene Szenarien am besten geeignet ist. Ein <xref:System.Windows.Documents.Table> für die Verwendung innerhalb von fortlaufendem Inhalten vorgesehen (finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md) Weitere Informationen zum fortlaufenden Inhalt). Raster eignen sich am besten für den Einsatz in Formularen (also eigentlich überall dort, wo es keinen fortlaufenden Inhalt gibt). Innerhalb einer <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> unterstützt flow Verhalten wie Paginierung, Spaltenumbruch und Inhaltsauswahl, während eine <xref:System.Windows.Controls.Grid> nicht. Ein <xref:System.Windows.Controls.Grid> auf der anderen Seite ist außerhalb des am besten verwendet eine <xref:System.Windows.Documents.FlowDocument> vielen Gründen <xref:System.Windows.Controls.Grid> fügt Elemente basierend auf einem Zeilen- und Spaltenindexes <xref:System.Windows.Documents.Table> nicht. Die <xref:System.Windows.Controls.Grid> Element ermöglicht die Überlagerung von untergeordnetem Inhalt, sodass mehr als ein Element in einer einzelnen "Zelle" enthalten sein können <xref:System.Windows.Documents.Table> unterstützt die Überlagerung nicht. Untergeordnete Elemente einer <xref:System.Windows.Controls.Grid> können absolut zum Bereich ihrer "zellenbegrenzungen" positioniert werden. <xref:System.Windows.Documents.Table> Dieses Feature wird nicht unterstützt werden. Zum Schluss eine <xref:System.Windows.Controls.Grid> weniger Ressourcen benötigt, wird eine <xref:System.Windows.Documents.Table> . also überlegen eine <xref:System.Windows.Controls.Grid> zur Verbesserung der Leistung.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Grundlegende Tabellenstruktur  
 <xref:System.Windows.Documents.Table> ermöglicht die rasterbasierte Darstellung von Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> Elemente). <xref:System.Windows.Documents.TableColumn> -Elemente hosten keinen Inhalt. Sie definieren lediglich Spalten und deren Eigenschaften. <xref:System.Windows.Documents.TableRow> Elemente müssen gehostet werden, einem <xref:System.Windows.Documents.TableRowGroup> -Element, das eine Gruppierung von Zeilen für die Tabelle definiert. <xref:System.Windows.Documents.TableCell> Elemente, die enthalten den eigentlichen Inhalt der Tabelle angezeigt werden, müssen gehostet werden, einem <xref:System.Windows.Documents.TableRow> Element. <xref:System.Windows.Documents.TableCell> kann nur Elemente enthalten, die abgeleitet <xref:System.Windows.Documents.Block>.  Gültige untergeordnete Elemente für eine <xref:System.Windows.Documents.TableCell> enthalten.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell> -Elemente hosten Textinhalt möglicherweise nicht direkt. Weitere Informationen über die Kapselungsregeln für fortlaufenden Inhaltselemente wie <xref:System.Windows.Documents.TableCell>, finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table> ähnelt der <xref:System.Windows.Controls.Grid> Element aber weist mehr Funktionen und erfordert daher höheren Ressourcenaufwand.  
  
 Das folgende Beispiel definiert eine einfache 2 x 3-Tabelle mit [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Rendern einer Basistabelle](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Tabellenkapselung  
 <xref:System.Windows.Documents.Table> leitet sich von der <xref:System.Windows.Documents.Block> -Element, und die allgemeinen Regeln für <xref:System.Windows.Documents.Block> Ebene von Elementen.  Ein <xref:System.Windows.Documents.Table> Element kann eines der folgenden Elemente enthalten sein:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Zeilengruppen  
 Die <xref:System.Windows.Documents.TableRowGroup> Element bietet eine Möglichkeit zum beliebigen Gruppieren von Zeilen in einer Tabelle; jede Zeile in einer Tabelle einer zeilengruppierung angehören muss.  Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.  Eine häufige Verwendung für Zeilengruppen ist die Trennung von Zeilen mit verschiedenen Zwecken, um z.B. Titel, Kopfzeilen und Fußzeilen vom Hauptinhalt der Tabelle zu trennen.  
  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] zum Definieren einer Tabelle mit formatierten Kopf- und Fußzeile Zeilen.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Tabellenzeilengruppen](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>Hintergrundrendering-Rangfolge  
 Tabellenelemente rendern in der folgenden Reihenfolge (Z-Reihenfolge, vom niedrigsten zum höchsten). Diese Reihenfolge kann nicht geändert werden. Beispielsweise gibt es keine „Z-Reihenfolge“-Eigenschaft für diese Elemente, die Sie zum Überschreiben dieser festgelegten Reihenfolge verwenden können.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 Betrachten Sie das folgende Beispiel, das Hintergrundfarben für jedes dieser Elemente in einer Tabelle definiert.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel (nur Hintergrundfarben werden angezeigt) gerendert wird.  
  
 ![Screenshot: Tabelle z&#45;Reihenfolge](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Überspannen von Zeilen oder Spalten  
 Tabellenzellen können so konfiguriert werden, um mehrere Zeilen oder Spalten mit umfassen die <xref:System.Windows.Documents.TableCell.RowSpan%2A> oder <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> beziehungsweise.  
  
 Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten umfasst.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot: Zelle umfasst alle drei Spalten](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Erstellen einer Tabelle mit Code  
 Die folgenden Beispiele zeigen, wie Sie programmgesteuert erstellen eine <xref:System.Windows.Documents.Table> und mit Inhalt füllen. Die Inhalte der Tabelle sind in fünf Zeilen aufgeteilt (dargestellt durch <xref:System.Windows.Documents.TableRow> in enthaltenen Objekte eine <xref:System.Windows.Documents.Table.RowGroups%2A> Objekt) und sechs Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Objekte). Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.  Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften. Tabellenzellen enthalten den eigentlichen Inhalt, der der Text, Bildern oder nahezu jedem anderen bestehen kann [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Element.  
  
 Zuerst eine <xref:System.Windows.Documents.FlowDocument> wird erstellt, auf Host der <xref:System.Windows.Documents.Table>, und ein neues <xref:System.Windows.Documents.Table> wird erstellt und hinzugefügt werden, auf den Inhalt des der <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Als Nächstes sechs <xref:System.Windows.Documents.TableColumn> Objekte erstellt und der Tabelle hinzugefügt werden <xref:System.Windows.Documents.Table.Columns%2A> Sammlung mit angewandter Formatierung.  
  
> [!NOTE]
>  Beachten Sie, dass der tabellenspezifischen <xref:System.Windows.Documents.Table.Columns%2A> Auflistung standardmäßige nullbasierte Indizierung verwendet.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.  Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.  Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.  Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
- [Definieren einer Tabelle mit XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)
- [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Verwenden von fortlaufenden Inhaltselementen](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
