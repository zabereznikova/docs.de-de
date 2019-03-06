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
ms.openlocfilehash: e202fe839de547145c36a5664b62c350f40bfce6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379011"
---
# <a name="table-overview"></a><span data-ttu-id="f0775-102">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="f0775-102">Table Overview</span></span>
<span data-ttu-id="f0775-103"><xref:System.Windows.Documents.Table> ist ein Element auf Blockebene, die rasterbasierte Darstellung von Flussdokumentinhalten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0775-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="f0775-104">Die Flexibilität dieses Elements macht es nicht nur sehr hilfreich, sondern auch schwieriger zu verstehen und richtig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0775-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="f0775-105">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="f0775-105">This topic contains the following sections.</span></span>  
  
-   [<span data-ttu-id="f0775-106">Grundlagen zu Tabellen</span><span class="sxs-lookup"><span data-stu-id="f0775-106">Table Basics</span></span>](#table_basics)  
  
-   [<span data-ttu-id="f0775-107">Worin unterscheidet sich eine Tabelle von einem Raster?</span><span class="sxs-lookup"><span data-stu-id="f0775-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
-   [<span data-ttu-id="f0775-108">Grundlegende Tabellenstruktur</span><span class="sxs-lookup"><span data-stu-id="f0775-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
-   [<span data-ttu-id="f0775-109">Tabellenkapselung</span><span class="sxs-lookup"><span data-stu-id="f0775-109">Table Containment</span></span>](#table_containment)  
  
-   [<span data-ttu-id="f0775-110">Zeilengruppen</span><span class="sxs-lookup"><span data-stu-id="f0775-110">Row Groupings</span></span>](#row_groupings)  
  
-   [<span data-ttu-id="f0775-111">Hintergrundrendering-Rangfolge</span><span class="sxs-lookup"><span data-stu-id="f0775-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
-   [<span data-ttu-id="f0775-112">Überspannen von Zeilen oder Spalten</span><span class="sxs-lookup"><span data-stu-id="f0775-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
-   [<span data-ttu-id="f0775-113">Erstellen einer Tabelle mit Code</span><span class="sxs-lookup"><span data-stu-id="f0775-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
-   <span data-ttu-id="f0775-114">[Verwandte Themen]</span><span class="sxs-lookup"><span data-stu-id="f0775-114">[Related Topics]</span></span> 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a><span data-ttu-id="f0775-115">Grundlagen zu Tabellen</span><span class="sxs-lookup"><span data-stu-id="f0775-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="f0775-116">Worin unterscheidet sich eine Tabelle von einem Raster?</span><span class="sxs-lookup"><span data-stu-id="f0775-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="f0775-117"><xref:System.Windows.Documents.Table> und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, aber jede für verschiedene Szenarien am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f0775-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="f0775-118">Ein <xref:System.Windows.Documents.Table> für die Verwendung innerhalb von fortlaufendem Inhalten vorgesehen (finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md) Weitere Informationen zum fortlaufenden Inhalt).</span><span class="sxs-lookup"><span data-stu-id="f0775-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="f0775-119">Raster eignen sich am besten für den Einsatz in Formularen (also eigentlich überall dort, wo es keinen fortlaufenden Inhalt gibt).</span><span class="sxs-lookup"><span data-stu-id="f0775-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="f0775-120">Innerhalb einer <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> unterstützt flow Verhalten wie Paginierung, Spaltenumbruch und Inhaltsauswahl, während eine <xref:System.Windows.Controls.Grid> nicht.</span><span class="sxs-lookup"><span data-stu-id="f0775-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="f0775-121">Ein <xref:System.Windows.Controls.Grid> auf der anderen Seite ist außerhalb des am besten verwendet eine <xref:System.Windows.Documents.FlowDocument> vielen Gründen <xref:System.Windows.Controls.Grid> fügt Elemente basierend auf einem Zeilen- und Spaltenindexes <xref:System.Windows.Documents.Table> nicht.</span><span class="sxs-lookup"><span data-stu-id="f0775-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="f0775-122">Die <xref:System.Windows.Controls.Grid> Element ermöglicht die Überlagerung von untergeordnetem Inhalt, sodass mehr als ein Element in einer einzelnen "Zelle" enthalten sein können</span><span class="sxs-lookup"><span data-stu-id="f0775-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="f0775-123"><xref:System.Windows.Documents.Table> unterstützt die Überlagerung nicht.</span><span class="sxs-lookup"><span data-stu-id="f0775-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="f0775-124">Untergeordnete Elemente einer <xref:System.Windows.Controls.Grid> können absolut zum Bereich ihrer "zellenbegrenzungen" positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="f0775-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="f0775-125"><xref:System.Windows.Documents.Table> Dieses Feature wird nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f0775-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="f0775-126">Zum Schluss eine <xref:System.Windows.Controls.Grid> weniger Ressourcen benötigt, wird eine <xref:System.Windows.Documents.Table> . also überlegen eine <xref:System.Windows.Controls.Grid> zur Verbesserung der Leistung.</span><span class="sxs-lookup"><span data-stu-id="f0775-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a><span data-ttu-id="f0775-127">Grundlegende Tabellenstruktur</span><span class="sxs-lookup"><span data-stu-id="f0775-127">Basic Table Structure</span></span>  
 <span data-ttu-id="f0775-128"><xref:System.Windows.Documents.Table> ermöglicht die rasterbasierte Darstellung von Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Elemente) und Zeilen (dargestellt durch <xref:System.Windows.Documents.TableRow> Elemente).</span><span class="sxs-lookup"><span data-stu-id="f0775-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="f0775-129"><xref:System.Windows.Documents.TableColumn> -Elemente hosten keinen Inhalt. Sie definieren lediglich Spalten und deren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f0775-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="f0775-130"><xref:System.Windows.Documents.TableRow> Elemente müssen gehostet werden, einem <xref:System.Windows.Documents.TableRowGroup> -Element, das eine Gruppierung von Zeilen für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="f0775-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="f0775-131"><xref:System.Windows.Documents.TableCell> Elemente, die enthalten den eigentlichen Inhalt der Tabelle angezeigt werden, müssen gehostet werden, einem <xref:System.Windows.Documents.TableRow> Element.</span><span class="sxs-lookup"><span data-stu-id="f0775-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="f0775-132"><xref:System.Windows.Documents.TableCell> kann nur Elemente enthalten, die abgeleitet <xref:System.Windows.Documents.Block>.</span><span class="sxs-lookup"><span data-stu-id="f0775-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="f0775-133">Gültige untergeordnete Elemente für eine <xref:System.Windows.Documents.TableCell> enthalten.</span><span class="sxs-lookup"><span data-stu-id="f0775-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <span data-ttu-id="f0775-134"><xref:System.Windows.Documents.TableCell> -Elemente hosten Textinhalt möglicherweise nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="f0775-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="f0775-135">Weitere Informationen über die Kapselungsregeln für fortlaufenden Inhaltselemente wie <xref:System.Windows.Documents.TableCell>, finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f0775-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0775-136"><xref:System.Windows.Documents.Table> ähnelt der <xref:System.Windows.Controls.Grid> Element aber weist mehr Funktionen und erfordert daher höheren Ressourcenaufwand.</span><span class="sxs-lookup"><span data-stu-id="f0775-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="f0775-137">Das folgende Beispiel definiert eine einfache 2 x 3-Tabelle mit [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0775-137">The following example defines a simple 2 x 3 table with [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="f0775-138">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="f0775-138">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="f0775-139">![Screenshot: Rendern einer Basistabelle](./media/basictablerrender.png "BasicTablerRender")</span><span class="sxs-lookup"><span data-stu-id="f0775-139">![Screenshot: Render a basic table](./media/basictablerrender.png "BasicTablerRender")</span></span>  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a><span data-ttu-id="f0775-140">Tabellenkapselung</span><span class="sxs-lookup"><span data-stu-id="f0775-140">Table Containment</span></span>  
 <span data-ttu-id="f0775-141"><xref:System.Windows.Documents.Table> leitet sich von der <xref:System.Windows.Documents.Block> -Element, und die allgemeinen Regeln für <xref:System.Windows.Documents.Block> Ebene von Elementen.</span><span class="sxs-lookup"><span data-stu-id="f0775-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="f0775-142">Ein <xref:System.Windows.Documents.Table> Element kann eines der folgenden Elemente enthalten sein:</span><span class="sxs-lookup"><span data-stu-id="f0775-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a><span data-ttu-id="f0775-143">Zeilengruppen</span><span class="sxs-lookup"><span data-stu-id="f0775-143">Row Groupings</span></span>  
 <span data-ttu-id="f0775-144">Die <xref:System.Windows.Documents.TableRowGroup> Element bietet eine Möglichkeit zum beliebigen Gruppieren von Zeilen in einer Tabelle; jede Zeile in einer Tabelle einer zeilengruppierung angehören muss.</span><span class="sxs-lookup"><span data-stu-id="f0775-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="f0775-145">Zeilen in einer Zeilengruppe dienen häufig einem gemeinsamen Zweck und können als Gruppe formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0775-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="f0775-146">Eine häufige Verwendung für Zeilengruppen ist die Trennung von Zeilen mit verschiedenen Zwecken, um z.B. Titel, Kopfzeilen und Fußzeilen vom Hauptinhalt der Tabelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f0775-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="f0775-147">Im folgenden Beispiel wird [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] zum Definieren einer Tabelle mit formatierten Kopf- und Fußzeile Zeilen.</span><span class="sxs-lookup"><span data-stu-id="f0775-147">The following example uses [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="f0775-148">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="f0775-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="f0775-149">![Screenshot: Tabellenzeilengruppen](./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="f0775-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a><span data-ttu-id="f0775-150">Hintergrundrendering-Rangfolge</span><span class="sxs-lookup"><span data-stu-id="f0775-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="f0775-151">Tabellenelemente rendern in der folgenden Reihenfolge (Z-Reihenfolge, vom niedrigsten zum höchsten).</span><span class="sxs-lookup"><span data-stu-id="f0775-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="f0775-152">Diese Reihenfolge kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0775-152">This order cannot be changed.</span></span> <span data-ttu-id="f0775-153">Beispielsweise gibt es keine „Z-Reihenfolge“-Eigenschaft für diese Elemente, die Sie zum Überschreiben dieser festgelegten Reihenfolge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f0775-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="f0775-154">Betrachten Sie das folgende Beispiel, das Hintergrundfarben für jedes dieser Elemente in einer Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="f0775-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="f0775-155">Die folgende Abbildung zeigt, wie dieses Beispiel (nur Hintergrundfarben werden angezeigt) gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="f0775-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="f0775-156">![Screenshot: Tabelle z&#45;Reihenfolge](./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="f0775-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="f0775-157">Überspannen von Zeilen oder Spalten</span><span class="sxs-lookup"><span data-stu-id="f0775-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="f0775-158">Tabellenzellen können so konfiguriert werden, um mehrere Zeilen oder Spalten mit umfassen die <xref:System.Windows.Documents.TableCell.RowSpan%2A> oder <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> beziehungsweise.</span><span class="sxs-lookup"><span data-stu-id="f0775-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="f0775-159">Betrachten Sie das folgende Beispiel, in dem eine Zelle drei Spalten umfasst.</span><span class="sxs-lookup"><span data-stu-id="f0775-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="f0775-160">Die folgende Abbildung zeigt, wie dieses Beispiel gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="f0775-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="f0775-161">![Screenshot: Zelle umfasst alle drei Spalten](./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="f0775-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a><span data-ttu-id="f0775-162">Erstellen einer Tabelle mit Code</span><span class="sxs-lookup"><span data-stu-id="f0775-162">Building a Table With Code</span></span>  
 <span data-ttu-id="f0775-163">Die folgenden Beispiele zeigen, wie Sie programmgesteuert erstellen eine <xref:System.Windows.Documents.Table> und mit Inhalt füllen.</span><span class="sxs-lookup"><span data-stu-id="f0775-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="f0775-164">Die Inhalte der Tabelle sind in fünf Zeilen aufgeteilt (dargestellt durch <xref:System.Windows.Documents.TableRow> in enthaltenen Objekte eine <xref:System.Windows.Documents.Table.RowGroups%2A> Objekt) und sechs Spalten (dargestellt durch <xref:System.Windows.Documents.TableColumn> Objekte).</span><span class="sxs-lookup"><span data-stu-id="f0775-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="f0775-165">Die Zeilen werden für die unterschiedlichen Präsentationszwecke verwendet, einschließlich einer Titelzeile für die Betitelung der gesamten Tabelle, einer Kopfzeile zur Beschreibung der Spalten in der Tabelle und einer Fußzeile mit Zusammenfassungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="f0775-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="f0775-166">Beachten Sie, dass die Angabe der Zeilen „Titel“, „Kopf“ und „Fuß“ in der Tabelle nicht vorhanden ist. Hierbei handelt es sich nur um Zeilen mit unterschiedlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f0775-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="f0775-167">Tabellenzellen enthalten den eigentlichen Inhalt, der der Text, Bildern oder nahezu jedem anderen bestehen kann [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Element.</span><span class="sxs-lookup"><span data-stu-id="f0775-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="f0775-168">Zuerst eine <xref:System.Windows.Documents.FlowDocument> wird erstellt, auf Host der <xref:System.Windows.Documents.Table>, und ein neues <xref:System.Windows.Documents.Table> wird erstellt und hinzugefügt werden, auf den Inhalt des der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="f0775-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="f0775-169">Als Nächstes sechs <xref:System.Windows.Documents.TableColumn> Objekte erstellt und der Tabelle hinzugefügt werden <xref:System.Windows.Documents.Table.Columns%2A> Sammlung mit angewandter Formatierung.</span><span class="sxs-lookup"><span data-stu-id="f0775-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0775-170">Beachten Sie, dass der tabellenspezifischen <xref:System.Windows.Documents.Table.Columns%2A> Auflistung standardmäßige nullbasierte Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0775-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="f0775-171">Als Nächstes wird eine Titelzeile erstellt und mit angewandter Formatierung zur Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f0775-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="f0775-172">Die Titelzeile enthält eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="f0775-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="f0775-173">Als Nächstes eine Kopfzeile erstellt und zur Tabelle hinzugefügt, und die Zellen in der Kopfzeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="f0775-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="f0775-174">Als Nächstes wird eine Zeile für Daten erstellt und zur Tabelle hinzugefügt, und die Zellen in dieser Zeile werden erstellt und mit Inhalt gefüllt.</span><span class="sxs-lookup"><span data-stu-id="f0775-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="f0775-175">Das Erstellen dieser Zeile ähnelt der Erstellung der Kopfzeile, mit einer leicht verschiedenen angewandten Formatierung.</span><span class="sxs-lookup"><span data-stu-id="f0775-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="f0775-176">Schließlich wird eine Fußzeile erstellt, hinzugefügt und formatiert.</span><span class="sxs-lookup"><span data-stu-id="f0775-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="f0775-177">Genau wie die Titelzeile enthält die Fußzeile eine einzelne Zelle, die alle sechs Spalten in der Tabelle umfasst.</span><span class="sxs-lookup"><span data-stu-id="f0775-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="f0775-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0775-178">See also</span></span>
- [<span data-ttu-id="f0775-179">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="f0775-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="f0775-180">Definieren einer Tabelle mit XAML</span><span class="sxs-lookup"><span data-stu-id="f0775-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="f0775-181">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="f0775-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="f0775-182">Verwenden von fortlaufenden Inhaltselementen</span><span class="sxs-lookup"><span data-stu-id="f0775-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)
