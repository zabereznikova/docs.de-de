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
ms.openlocfilehash: 4bd747cea43755116c56b16f1de9a6ffb59935ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187273"
---
# <a name="table-overview"></a>Übersicht über Tabellen
<xref:System.Windows.Documents.Table>ist ein Blockebenenelement, das die rasterbasierte Darstellung von Flow-Dokumentinhalten unterstützt. Die Flexibilität dieses Elements macht es nicht nur sehr hilfreich, sondern auch schwieriger zu verstehen und richtig zu verwenden.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Grundlagen zu Tabellen](#table_basics)  
  
- [Worin unterscheidet sich eine Tabelle von einem Raster?](#table_vs_Grid)  
  
- [Grundlegende Tabellenstruktur](#basic_table_structure)  
  
- [Tabellenkapselung](#table_containment)  
  
- [Zeilengruppen](#row_groupings)  
  
- [Hintergrundrendering-Rangfolge](#rendering_precedence)  
  
- [Überspannen von Zeilen oder Spalten](#spanning_rows_or_columns)  
  
- [Erstellen einer Tabelle mit Code](#building_a_table_with_code)  
  
- [Verwandte Themen]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>Grundlagen zu Tabellen  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>Worin unterscheidet sich eine Tabelle von einem Raster?  
 <xref:System.Windows.Documents.Table>und <xref:System.Windows.Controls.Grid> teilen Sie einige gemeinsame Funktionen, aber jede ist am besten für verschiedene Szenarien geeignet. A <xref:System.Windows.Documents.Table> ist für die Verwendung innerhalb von Flow-Inhalten konzipiert (weitere Informationen zum Flow-Inhalt finden Sie unter [Flussdokumentübersicht).](flow-document-overview.md) Raster eignen sich am Besten für die Verwendung in Formularen (im Grunde außerhalb von fortlaufendem Inhalt). Innerhalb <xref:System.Windows.Documents.FlowDocument>von <xref:System.Windows.Documents.Table> unterstützt Flow Content-Verhalten wie Paginierung, Spaltenreflow <xref:System.Windows.Controls.Grid> und Inhaltsauswahl, während a nicht. A <xref:System.Windows.Controls.Grid> hingegen wird am besten außerhalb eines <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.Grid> aus vielen Gründen verwendet, einschließlich <xref:System.Windows.Documents.Table> der Hinzusagung von Elementen, die auf einem Zeilen- und Spaltenindex basieren, nicht. Das <xref:System.Windows.Controls.Grid> Element ermöglicht die Schichtung von untergeordneten Inhalten, sodass mehr als ein Element innerhalb einer einzelnen "Zelle" vorhanden ist. <xref:System.Windows.Documents.Table>unterstützt keine Layering. Untergeordnete Elemente <xref:System.Windows.Controls.Grid> eines können absolut relativ zum Bereich ihrer "Zell"-Grenzen positioniert werden. <xref:System.Windows.Documents.Table>unterstützt diese Funktion nicht. Schließlich benötigt <xref:System.Windows.Controls.Grid> a weniger <xref:System.Windows.Documents.Table> Ressourcen als <xref:System.Windows.Controls.Grid> eine, die sie verwenden sollten, um die Leistung zu verbessern.  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>Grundlegende Tabellenstruktur  
 <xref:System.Windows.Documents.Table>bietet eine gitterbasierte Darstellung, die <xref:System.Windows.Documents.TableColumn> aus Spalten (dargestellt <xref:System.Windows.Documents.TableRow> durch Elemente) und Zeilen (dargestellt durch Elemente) besteht. <xref:System.Windows.Documents.TableColumn>Elemente hosten keinen Inhalt; Sie definieren einfach Spalten und Merkmale von Spalten. <xref:System.Windows.Documents.TableRow>Elemente müssen in <xref:System.Windows.Documents.TableRowGroup> einem Element gehostet werden, das eine Gruppierung von Zeilen für die Tabelle definiert. <xref:System.Windows.Documents.TableCell>Elemente, die den tatsächlichen Inhalt enthalten, der von der <xref:System.Windows.Documents.TableRow> Tabelle angezeigt werden soll, müssen in einem Element gehostet werden. <xref:System.Windows.Documents.TableCell>dürfen nur Elemente enthalten, <xref:System.Windows.Documents.Block>die von stammen.  Gültige untergeordnete Elemente <xref:System.Windows.Documents.TableCell> für ein Include.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>Elemente dürfen Textinhalte nicht direkt hosten. Weitere Informationen zu den Containment-Regeln <xref:System.Windows.Documents.TableCell>für Flow-Inhaltselemente wie , finden Sie unter [Flussdokumentübersicht](flow-document-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>ist dem <xref:System.Windows.Controls.Grid> Element ähnlich, verfügt jedoch über mehr Funktionen und erfordert daher einen höheren Ressourcenaufwand.  
  
 Im folgenden Beispiel wird eine einfache Tabelle 2 x 3 mit XAML definiert.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Screenshot, der zeigt, wie eine basiskgrundlegende Tabelle gerendert wird.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>Tabellenkapselung  
 <xref:System.Windows.Documents.Table>abgeleitet vom <xref:System.Windows.Documents.Block> Element und hält sich an die <xref:System.Windows.Documents.Block> gemeinsamen Regeln für Ebenenelemente.  Ein <xref:System.Windows.Documents.Table> Element kann in einem der folgenden Elemente enthalten sein:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>Zeilengruppen  
 Das <xref:System.Windows.Documents.TableRowGroup> Element bietet eine Möglichkeit, Zeilen in einer Tabelle willkürlich zu gruppieren. Jede Zeile in einer Tabelle muss zu einer Zeilengruppierung gehören.  Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.  Eine häufige Verwendung für Zeilengruppen ist die Trennung von Zeilen mit verschiedenen Zwecken, um z.B. Titel, Kopfzeilen und Fußzeilen vom Hauptinhalt der Tabelle zu trennen.  
  
 Im folgenden Beispiel wird XAML verwendet, um eine Tabelle mit formatierten Kopf- und Fußzeilen zu definieren.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Tabellenzeilengruppen](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a>Hintergrundrendering-Rangfolge  
 Tabellenelemente rendern in der folgenden Reihenfolge (Z-Reihenfolge, vom niedrigsten zum höchsten). Diese Reihenfolge kann nicht geändert werden. Beispielsweise gibt es keine „Z-Reihenfolge“-Eigenschaft für diese Elemente, die Sie zum Überschreiben dieser festgelegten Reihenfolge verwenden können.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 Betrachten Sie das folgende Beispiel, das Hintergrundfarben für jedes dieser Elemente in einer Tabelle definiert.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel (nur Hintergrundfarben werden angezeigt) gerendert wird.  
  
 ![Screenshot: Tabelle z&#45;Reihenfolge](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>Überspannen von Zeilen oder Spalten  
 Tabellenzellen können so konfiguriert werden, dass sie <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> mehrere Zeilen oder Spalten mit den attributen bzw.  
  
 Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten umfasst.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Zelle umfasst alle drei Spalten](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>Erstellen einer Tabelle mit Code  
 Die folgenden Beispiele zeigen, wie <xref:System.Windows.Documents.Table> Sie ein programmgesteuertes Erstellen und Auffüllen mit Inhalten erstellen. Der Inhalt der Tabelle wird in fünf Zeilen <xref:System.Windows.Documents.TableRow> (dargestellt <xref:System.Windows.Documents.Table.RowGroups%2A> durch Objekte, die in <xref:System.Windows.Documents.TableColumn> einem Objekt enthalten sind) und sechs Spalten (dargestellt durch Objekte) unterteilt. Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.  Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften. Tabellenzellen enthalten den eigentlichen Inhalt, der aus Text, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Bildern oder fast jedem anderen Element bestehen kann.  
  
 Zuerst wird <xref:System.Windows.Documents.FlowDocument> eine erstellt, <xref:System.Windows.Documents.Table>um die <xref:System.Windows.Documents.Table> zu hosten, und <xref:System.Windows.Documents.FlowDocument>ein neues wird erstellt und dem Inhalt der hinzugefügt.  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Als Nächstes <xref:System.Windows.Documents.TableColumn> werden sechs Objekte erstellt und <xref:System.Windows.Documents.Table.Columns%2A> der Tabellensammlung hinzugefügt, wobei einige Formatierungen angewendet werden.  
  
> [!NOTE]
> Beachten Sie, dass <xref:System.Windows.Documents.Table.Columns%2A> die Auflistung der Tabelle die standardmäßige nullbasierte Indizierung verwendet.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.  Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.  Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.  Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Flussdokumente](flow-document-overview.md)
- [Definieren einer Tabelle mit XAML](how-to-define-a-table-with-xaml.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Verwenden von fortlaufenden Inhaltselementen](how-to-use-flow-content-elements.md)
