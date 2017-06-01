---
title: "&#220;bersicht &#252;ber Tabellen | Microsoft Docs"
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
  - "Dokumente, Tabellen"
  - "Fortlaufende Inhaltselemente [WPF], Tabelle"
  - "Tabellen"
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# &#220;bersicht &#252;ber Tabellen
<xref:System.Windows.Documents.Table> ist ein Element auf Blockebene, das die rasterbasierte Darstellung von Flussdokumentinhalten unterstützt.  Aufgrund seiner Flexibilität ist dieses Element sehr nützlich, seine richtige Anwendung ist jedoch relativ schwierig.  
  
 Dieses Thema enthält folgende Abschnitte.  
  
-   [Grundlagen zu Tabellen](#table_basics)  
  
-   [Was unterscheidet eine Tabelle von einem Raster?](#table_vs_Grid)  
  
-   [Grundlegende Tabellenstruktur](#basic_table_structure)  
  
-   [Tabellenkapselung](#table_containment)  
  
-   [Zeilengruppen](#row_groupings)  
  
-   [Hintergrundrendering\-Rangfolge](#rednering_precedence)  
  
-   [Überspannen von Zeilen oder Spalten](#spanning_rows_or_columns)  
  
-   [Erstellen einer Tabelle mit Code](#building_a_table_with_code)  
  
-   [Verwandte Themen](#see_also)  
  
<a name="table_basics"></a>   
## Grundlagen zu Tabellen  
  
<a name="table_vs_Grid"></a>   
### Was unterscheidet eine Tabelle von einem Raster?  
 <xref:System.Windows.Documents.Table> und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, sind jedoch beide für unterschiedliche Szenarien geeignet.  Eine <xref:System.Windows.Documents.Table> ist für die Verwendung innerhalb von fortlaufenden Inhalten vorgesehen. \(Weitere Informationen über fortlaufenden Inhalt finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).\)  Raster eignen sich am besten für die Verwendung in Formularen \(bzw. außerhalb von fortlaufendem Inhalt\).  In einem <xref:System.Windows.Documents.FlowDocument> unterstützt eine <xref:System.Windows.Documents.Table> verschiedene Verhaltensweisen von fortlaufendem Inhalt wie Paginierung, Tabellenflussrichtung und Inhaltsauswahl, ein <xref:System.Windows.Controls.Grid> dagegen unterstützt dies nicht.  Ein <xref:System.Windows.Controls.Grid> sollte aus verschiedenen Gründen außerhalb eines <xref:System.Windows.Documents.FlowDocument> verwendet werden. Unter anderem fügt ein <xref:System.Windows.Controls.Grid> im Gegensatz zu einer <xref:System.Windows.Documents.Table> Elemente auf Grundlage eines Zeilen\- und Spaltenindexes hinzu.  Das <xref:System.Windows.Controls.Grid>\-Element ermöglicht es, untergeordnete Inhalte überlagernd anzuordnen, sodass mehrere Elemente in einer "Zelle" enthalten sein können. <xref:System.Windows.Documents.Table> unterstützt die Überlagerung nicht.  Die untergeordneten Elemente für ein <xref:System.Windows.Controls.Grid>\-Element können absolut zum Bereich ihrer Zellenbegrenzung positioniert werden.  <xref:System.Windows.Documents.Table> unterstützt dieses Feature nicht.  Schließlich erfordert ein <xref:System.Windows.Controls.Grid> weniger Ressourcen als eine <xref:System.Windows.Documents.Table>. Deshalb sollten Sie zur Verbesserung der Leistung die Verwendung von einem <xref:System.Windows.Controls.Grid> in Betracht ziehen.  
  
<a name="basic_table_structure"></a>   
### Grundlegende Tabellenstruktur  
 <xref:System.Windows.Documents.Table> ermöglicht die rasterbasierte Darstellung von Spalten \(dargestellt durch <xref:System.Windows.Documents.TableColumn>\-Elemente\) und Zeilen \(dargestellt durch <xref:System.Windows.Documents.TableRow>\-Elemente\).  <xref:System.Windows.Documents.TableColumn>\-Elemente hosten keinen Inhalt. Sie dienen lediglich zur Definition von Spalten und deren Eigenschaften.  <xref:System.Windows.Documents.TableRow>\-Elemente müssen in einem <xref:System.Windows.Documents.TableRowGroup>\-Element gehostet sein, das eine Zeilengruppe für die Tabelle definiert.  <xref:System.Windows.Documents.TableCell>\-Elemente, die den eigentlichen Inhalt beinhalten, der von der Tabelle dargestellt werden soll, müssen in einem <xref:System.Windows.Documents.TableRow>\-Element gehostet sein.  <xref:System.Windows.Documents.TableCell> kann nur Elemente beinhalten, die von <xref:System.Windows.Documents.Block> abgeleitet sind.  Beispiele für gültige untergeordnete Elemente für eine <xref:System.Windows.Documents.TableCell>:  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell>\-Elemente hosten Textinhalt möglicherweise nicht direkt.  Weitere Informationen über die Kapselungsregeln für fortlaufende Inhaltselemente wie <xref:System.Windows.Documents.TableCell> finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table> ähnelt dem <xref:System.Windows.Controls.Grid>\-Element, besitzt jedoch mehr Fähigkeiten und benötigt deshalb mehr Ressourcen.  
  
 Im folgenden Beispiel wird eine einfache 2x3\-Tabelle mit [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] definiert.  
  
 [!code-xml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Rendern einer Basistabelle](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### Tabellenkapselung  
 <xref:System.Windows.Documents.Table> wird vom <xref:System.Windows.Documents.Block>\-Element abgeleitet und befolgt die allgemeinen Regeln für Elemente auf <xref:System.Windows.Documents.Block>\-Ebene.  Ein <xref:System.Windows.Documents.Table>\-Element ist möglicherweise in einem der folgenden Elemente enthalten:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### Zeilengruppen  
 Mit dem <xref:System.Windows.Documents.TableRowGroup>\-Element können Zeilen in einer Tabelle beliebig gruppiert werden, wobei jede Zeile einer Tabelle zu einer Zeilengruppierung gehören muss.  Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.  Häufig werden durch Zeilengruppen Zeilen verschiedenen Zwecks voneinander getrennt, z. B. der Hauptinhalt der Tabelle vom Titel, der Überschrift und den Fußzeilen.  
  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] verwendet, um eine Tabelle mit formatierten Kopf\- und Fußzeilen zu definieren.  
  
 [!code-xml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Tabellenzeilengruppen](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table\_RowGroups")  
  
<a name="renderning_precedence"></a>   
### Hintergrundrendering\-Rangfolge  
 Tabellenelemente rendern in der folgenden Reihenfolge \([z\-Reihenfolge](GTMT), vom niedrigsten zum höchsten\).  Diese Reihenfolge kann nicht geändert werden.  Zum Beispiel gibt es keine "z\-Reihenfolge"\-Eigenschaft für diese Elemente, die zum Überschreiben dieser festgelegten Reihenfolge verwendet werden könnte.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 Betrachten Sie das folgende Beispiel, in dem Hintergrundfarben für jedes dieser Elemente innerhalb einer Tabelle definiert werden.  
  
 [!code-xml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 Die folgende Abbildung veranschaulicht, wie dieses Beispiel rendert \(nur Hintergrundfarben werden angezeigt\).  
  
 ![Bildschirmabbildung: Tabellen&#45;Z&#45;Reihenfolge](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table\_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### Überspannen von Zeilen oder Spalten  
 Tabellenzellen können mit den Attributen <xref:System.Windows.Documents.TableCell.RowSpan%2A> oder <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> so konfiguriert werden, dass sie mehrere Zeilen oder Spalten überspannen.  
  
 Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten überspannt.  
  
 [!code-xml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 In der folgenden Abbildung wird gezeigt, wie dieses Beispiel gerendert wird.  
  
 ![Bildschirmabbildung: Zelle umfasst alle drei Spalten](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table\_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## Erstellen einer Tabelle mit Code  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Documents.Table> programmgesteuert erstellt und mit Inhalt gefüllt wird.  Die Inhalte der Tabelle sind auf fünf Zeilen \(dargestellt durch <xref:System.Windows.Documents.TableRow>\-Objekte, die in einem <xref:System.Windows.Documents.Table.RowGroups%2A>\-Objekt enthalten sind\) und sechs Spalten \(dargestellt durch <xref:System.Windows.Documents.TableColumn>\-Objekte\) aufgeteilt.  Die Zeilen werden für verschiedene Darstellungszwecke verwendet. Unter anderem gibt es eine Titelzeile, die als Überschrift für die gesamte Tabelle dient, eine Kopfzeile, die die Datenspalten der Tabelle beschreibt, und eine Fußzeile mit Zusammenfassungsinformationen.  Beachten Sie, dass die Begriffe "Titelzeile", "Kopfzeile" und "Fußzeile" keine spezifischen Bestandteile der Tabelle sind. Es handelt sich lediglich um Zeilen mit unterschiedlichen Eigenschaften.  Tabellenzellen enthalten den eigentlichen Inhalt, der aus Text, Bildern oder nahezu jedem beliebigen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Element bestehen kann.  
  
 Zuerst wird ein <xref:System.Windows.Documents.FlowDocument>, das die <xref:System.Windows.Documents.Table> hostet, sowie eine neue <xref:System.Windows.Documents.Table> erstellt und zu den Inhalten von <xref:System.Windows.Documents.FlowDocument> hinzugefügt.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Anschließend werden sechs <xref:System.Windows.Documents.TableColumn>\-Objekte erstellt und mit einigen Formatierungen zur <xref:System.Windows.Documents.Table.Columns%2A>\-Auflistung der Tabelle hinzugefügt.  
  
> [!NOTE]
>  Beachten Sie, dass die <xref:System.Windows.Documents.Table.Columns%2A>\-Auflistung der Tabelle nullbasierte Standardindizierung verwendet.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Anschließend wird eine Titelzeile erstellt und mit etwas Formatierung zur Tabelle hinzugefügt.  Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle überspannt.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Anschließend wird ein Header erstellt und zur Tabelle hinzugefügt. Die Zellen im Header werden erstellt und mit Inhalt gefüllt.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Anschließend wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt. Die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.  Das Erstellen dieser Zeile ähnelt der Erstellung des Headers, mit leichten Unterschieden bei der Formatierung.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.  Genau wie die Titelzeile enthält auch die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle überspannt.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## Siehe auch  
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Definieren einer Tabelle mit XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Verwenden von fortlaufenden Inhaltselementen](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)