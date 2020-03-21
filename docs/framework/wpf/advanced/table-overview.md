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
# <a name="table-overview"></a><span data-ttu-id="5add6-102">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="5add6-102">Table Overview</span></span>
<span data-ttu-id="5add6-103"><xref:System.Windows.Documents.Table>ist ein Blockebenenelement, das die rasterbasierte Darstellung von Flow-Dokumentinhalten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5add6-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="5add6-104">Die Flexibilität dieses Elements macht es nicht nur sehr hilfreich, sondern auch schwieriger zu verstehen und richtig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5add6-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="5add6-105">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="5add6-105">This topic contains the following sections.</span></span>  
  
- [<span data-ttu-id="5add6-106">Grundlagen zu Tabellen</span><span class="sxs-lookup"><span data-stu-id="5add6-106">Table Basics</span></span>](#table_basics)  
  
- [<span data-ttu-id="5add6-107">Worin unterscheidet sich eine Tabelle von einem Raster?</span><span class="sxs-lookup"><span data-stu-id="5add6-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
- [<span data-ttu-id="5add6-108">Grundlegende Tabellenstruktur</span><span class="sxs-lookup"><span data-stu-id="5add6-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
- [<span data-ttu-id="5add6-109">Tabellenkapselung</span><span class="sxs-lookup"><span data-stu-id="5add6-109">Table Containment</span></span>](#table_containment)  
  
- [<span data-ttu-id="5add6-110">Zeilengruppen</span><span class="sxs-lookup"><span data-stu-id="5add6-110">Row Groupings</span></span>](#row_groupings)  
  
- [<span data-ttu-id="5add6-111">Hintergrundrendering-Rangfolge</span><span class="sxs-lookup"><span data-stu-id="5add6-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
- [<span data-ttu-id="5add6-112">Überspannen von Zeilen oder Spalten</span><span class="sxs-lookup"><span data-stu-id="5add6-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
- [<span data-ttu-id="5add6-113">Erstellen einer Tabelle mit Code</span><span class="sxs-lookup"><span data-stu-id="5add6-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
- <span data-ttu-id="5add6-114">[Verwandte Themen]</span><span class="sxs-lookup"><span data-stu-id="5add6-114">[Related Topics]</span></span>
  
<a name="table_basics"></a>
## <a name="table-basics"></a><span data-ttu-id="5add6-115">Grundlagen zu Tabellen</span><span class="sxs-lookup"><span data-stu-id="5add6-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="5add6-116">Worin unterscheidet sich eine Tabelle von einem Raster?</span><span class="sxs-lookup"><span data-stu-id="5add6-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="5add6-117"><xref:System.Windows.Documents.Table>und <xref:System.Windows.Controls.Grid> teilen Sie einige gemeinsame Funktionen, aber jede ist am besten für verschiedene Szenarien geeignet.</span><span class="sxs-lookup"><span data-stu-id="5add6-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="5add6-118">A <xref:System.Windows.Documents.Table> ist für die Verwendung innerhalb von Flow-Inhalten konzipiert (weitere Informationen zum Flow-Inhalt finden Sie unter [Flussdokumentübersicht).](flow-document-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5add6-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="5add6-119">Raster eignen sich am Besten für die Verwendung in Formularen (im Grunde außerhalb von fortlaufendem Inhalt).</span><span class="sxs-lookup"><span data-stu-id="5add6-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="5add6-120">Innerhalb <xref:System.Windows.Documents.FlowDocument>von <xref:System.Windows.Documents.Table> unterstützt Flow Content-Verhalten wie Paginierung, Spaltenreflow <xref:System.Windows.Controls.Grid> und Inhaltsauswahl, während a nicht.</span><span class="sxs-lookup"><span data-stu-id="5add6-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="5add6-121">A <xref:System.Windows.Controls.Grid> hingegen wird am besten außerhalb eines <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.Grid> aus vielen Gründen verwendet, einschließlich <xref:System.Windows.Documents.Table> der Hinzusagung von Elementen, die auf einem Zeilen- und Spaltenindex basieren, nicht.</span><span class="sxs-lookup"><span data-stu-id="5add6-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="5add6-122">Das <xref:System.Windows.Controls.Grid> Element ermöglicht die Schichtung von untergeordneten Inhalten, sodass mehr als ein Element innerhalb einer einzelnen "Zelle" vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5add6-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="5add6-123"><xref:System.Windows.Documents.Table>unterstützt keine Layering.</span><span class="sxs-lookup"><span data-stu-id="5add6-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="5add6-124">Untergeordnete Elemente <xref:System.Windows.Controls.Grid> eines können absolut relativ zum Bereich ihrer "Zell"-Grenzen positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="5add6-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="5add6-125"><xref:System.Windows.Documents.Table>unterstützt diese Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="5add6-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="5add6-126">Schließlich benötigt <xref:System.Windows.Controls.Grid> a weniger <xref:System.Windows.Documents.Table> Ressourcen als <xref:System.Windows.Controls.Grid> eine, die sie verwenden sollten, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5add6-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a><span data-ttu-id="5add6-127">Grundlegende Tabellenstruktur</span><span class="sxs-lookup"><span data-stu-id="5add6-127">Basic Table Structure</span></span>  
 <span data-ttu-id="5add6-128"><xref:System.Windows.Documents.Table>bietet eine gitterbasierte Darstellung, die <xref:System.Windows.Documents.TableColumn> aus Spalten (dargestellt <xref:System.Windows.Documents.TableRow> durch Elemente) und Zeilen (dargestellt durch Elemente) besteht.</span><span class="sxs-lookup"><span data-stu-id="5add6-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="5add6-129"><xref:System.Windows.Documents.TableColumn>Elemente hosten keinen Inhalt; Sie definieren einfach Spalten und Merkmale von Spalten.</span><span class="sxs-lookup"><span data-stu-id="5add6-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="5add6-130"><xref:System.Windows.Documents.TableRow>Elemente müssen in <xref:System.Windows.Documents.TableRowGroup> einem Element gehostet werden, das eine Gruppierung von Zeilen für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="5add6-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="5add6-131"><xref:System.Windows.Documents.TableCell>Elemente, die den tatsächlichen Inhalt enthalten, der von der <xref:System.Windows.Documents.TableRow> Tabelle angezeigt werden soll, müssen in einem Element gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="5add6-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="5add6-132"><xref:System.Windows.Documents.TableCell>dürfen nur Elemente enthalten, <xref:System.Windows.Documents.Block>die von stammen.</span><span class="sxs-lookup"><span data-stu-id="5add6-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="5add6-133">Gültige untergeordnete Elemente <xref:System.Windows.Documents.TableCell> für ein Include.</span><span class="sxs-lookup"><span data-stu-id="5add6-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <span data-ttu-id="5add6-134"><xref:System.Windows.Documents.TableCell>Elemente dürfen Textinhalte nicht direkt hosten.</span><span class="sxs-lookup"><span data-stu-id="5add6-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="5add6-135">Weitere Informationen zu den Containment-Regeln <xref:System.Windows.Documents.TableCell>für Flow-Inhaltselemente wie , finden Sie unter [Flussdokumentübersicht](flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5add6-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5add6-136"><xref:System.Windows.Documents.Table>ist dem <xref:System.Windows.Controls.Grid> Element ähnlich, verfügt jedoch über mehr Funktionen und erfordert daher einen höheren Ressourcenaufwand.</span><span class="sxs-lookup"><span data-stu-id="5add6-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="5add6-137">Im folgenden Beispiel wird eine einfache Tabelle 2 x 3 mit XAML definiert.</span><span class="sxs-lookup"><span data-stu-id="5add6-137">The following example defines a simple 2 x 3 table with XAML.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="5add6-138">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="5add6-138">The following figure shows how this example renders.</span></span>  
  
 ![Screenshot, der zeigt, wie eine basiskgrundlegende Tabelle gerendert wird.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a><span data-ttu-id="5add6-140">Tabellenkapselung</span><span class="sxs-lookup"><span data-stu-id="5add6-140">Table Containment</span></span>  
 <span data-ttu-id="5add6-141"><xref:System.Windows.Documents.Table>abgeleitet vom <xref:System.Windows.Documents.Block> Element und hält sich an die <xref:System.Windows.Documents.Block> gemeinsamen Regeln für Ebenenelemente.</span><span class="sxs-lookup"><span data-stu-id="5add6-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="5add6-142">Ein <xref:System.Windows.Documents.Table> Element kann in einem der folgenden Elemente enthalten sein:</span><span class="sxs-lookup"><span data-stu-id="5add6-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a><span data-ttu-id="5add6-143">Zeilengruppen</span><span class="sxs-lookup"><span data-stu-id="5add6-143">Row Groupings</span></span>  
 <span data-ttu-id="5add6-144">Das <xref:System.Windows.Documents.TableRowGroup> Element bietet eine Möglichkeit, Zeilen in einer Tabelle willkürlich zu gruppieren. Jede Zeile in einer Tabelle muss zu einer Zeilengruppierung gehören.</span><span class="sxs-lookup"><span data-stu-id="5add6-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="5add6-145">Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="5add6-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="5add6-146">Eine häufige Verwendung für Zeilengruppen ist die Trennung von Zeilen mit verschiedenen Zwecken, um z.B. Titel, Kopfzeilen und Fußzeilen vom Hauptinhalt der Tabelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="5add6-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="5add6-147">Im folgenden Beispiel wird XAML verwendet, um eine Tabelle mit formatierten Kopf- und Fußzeilen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5add6-147">The following example uses XAML to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="5add6-148">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="5add6-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="5add6-149">![Bildschirmabbildung: Tabellenzeilengruppen](./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="5add6-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a><span data-ttu-id="5add6-150">Hintergrundrendering-Rangfolge</span><span class="sxs-lookup"><span data-stu-id="5add6-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="5add6-151">Tabellenelemente rendern in der folgenden Reihenfolge (Z-Reihenfolge, vom niedrigsten zum höchsten).</span><span class="sxs-lookup"><span data-stu-id="5add6-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="5add6-152">Diese Reihenfolge kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5add6-152">This order cannot be changed.</span></span> <span data-ttu-id="5add6-153">Beispielsweise gibt es keine „Z-Reihenfolge“-Eigenschaft für diese Elemente, die Sie zum Überschreiben dieser festgelegten Reihenfolge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5add6-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="5add6-154">Betrachten Sie das folgende Beispiel, das Hintergrundfarben für jedes dieser Elemente in einer Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="5add6-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="5add6-155">Die folgende Abbildung zeigt, wie dieses Beispiel (nur Hintergrundfarben werden angezeigt) gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="5add6-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="5add6-156">![Screenshot: Tabelle z&#45;Reihenfolge](./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="5add6-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="5add6-157">Überspannen von Zeilen oder Spalten</span><span class="sxs-lookup"><span data-stu-id="5add6-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="5add6-158">Tabellenzellen können so konfiguriert werden, dass sie <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> mehrere Zeilen oder Spalten mit den attributen bzw.</span><span class="sxs-lookup"><span data-stu-id="5add6-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="5add6-159">Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten umfasst.</span><span class="sxs-lookup"><span data-stu-id="5add6-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="5add6-160">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="5add6-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="5add6-161">![Bildschirmabbildung: Zelle umfasst alle drei Spalten](./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="5add6-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a><span data-ttu-id="5add6-162">Erstellen einer Tabelle mit Code</span><span class="sxs-lookup"><span data-stu-id="5add6-162">Building a Table With Code</span></span>  
 <span data-ttu-id="5add6-163">Die folgenden Beispiele zeigen, wie <xref:System.Windows.Documents.Table> Sie ein programmgesteuertes Erstellen und Auffüllen mit Inhalten erstellen.</span><span class="sxs-lookup"><span data-stu-id="5add6-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="5add6-164">Der Inhalt der Tabelle wird in fünf Zeilen <xref:System.Windows.Documents.TableRow> (dargestellt <xref:System.Windows.Documents.Table.RowGroups%2A> durch Objekte, die in <xref:System.Windows.Documents.TableColumn> einem Objekt enthalten sind) und sechs Spalten (dargestellt durch Objekte) unterteilt.</span><span class="sxs-lookup"><span data-stu-id="5add6-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="5add6-165">Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="5add6-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="5add6-166">Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5add6-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="5add6-167">Tabellenzellen enthalten den eigentlichen Inhalt, der aus Text, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Bildern oder fast jedem anderen Element bestehen kann.</span><span class="sxs-lookup"><span data-stu-id="5add6-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="5add6-168">Zuerst wird <xref:System.Windows.Documents.FlowDocument> eine erstellt, <xref:System.Windows.Documents.Table>um die <xref:System.Windows.Documents.Table> zu hosten, und <xref:System.Windows.Documents.FlowDocument>ein neues wird erstellt und dem Inhalt der hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5add6-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="5add6-169">Als Nächstes <xref:System.Windows.Documents.TableColumn> werden sechs Objekte erstellt und <xref:System.Windows.Documents.Table.Columns%2A> der Tabellensammlung hinzugefügt, wobei einige Formatierungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5add6-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5add6-170">Beachten Sie, dass <xref:System.Windows.Documents.Table.Columns%2A> die Auflistung der Tabelle die standardmäßige nullbasierte Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5add6-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="5add6-171">Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5add6-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="5add6-172">Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="5add6-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="5add6-173">Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="5add6-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="5add6-174">Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="5add6-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="5add6-175">Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.</span><span class="sxs-lookup"><span data-stu-id="5add6-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="5add6-176">Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.</span><span class="sxs-lookup"><span data-stu-id="5add6-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="5add6-177">Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="5add6-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="5add6-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5add6-178">See also</span></span>

- [<span data-ttu-id="5add6-179">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="5add6-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="5add6-180">Definieren einer Tabelle mit XAML</span><span class="sxs-lookup"><span data-stu-id="5add6-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="5add6-181">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="5add6-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="5add6-182">Verwenden von fortlaufenden Inhaltselementen</span><span class="sxs-lookup"><span data-stu-id="5add6-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)
