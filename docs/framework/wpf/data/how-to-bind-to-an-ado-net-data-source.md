---
title: 'Vorgehensweise: Binden an eine ADO.NET-Datenquelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 96f846db3f705972a4749460bf2c410483258572
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238424"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="1e7c2-102">Vorgehensweise: Binden an eine ADO.NET-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="1e7c2-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="1e7c2-103">Dieses Beispiel zeigt, wie Sie binden ein [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> Steuerelement an eine ADO.NET `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="1e7c2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e7c2-104">Example</span></span>

<span data-ttu-id="1e7c2-105">In diesem Beispiel wird ein `OleDbConnection`-Objekt zum Herstellen der Verbindung mit der Datenquelle verwendet, die als `Access MDB`-Datei in der Verbindungszeichenfolge angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="1e7c2-106">Nach dem Herstellen der Verbindung wird ein `OleDbDataAdapter`-Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="1e7c2-107">Das `OleDbDataAdapter`-Objekt führt eine SQL-Anweisung des Typs [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] aus, um das Recordset aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-107">The `OleDbDataAdapter` object executes a select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="1e7c2-108">Die Ergebnisse des [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)]-Befehls werden in einer `DataTable` für das `DataSet` gespeichert, indem die `Fill`-Methode von `OleDbDataAdapter` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-108">The results from the [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="1e7c2-109">Die `DataTable` in diesem Beispiel heißt `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="1e7c2-110">Anschließend wird im Beispiel die <xref:System.Windows.FrameworkElement.DataContext%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> auf die `DataSet` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="1e7c2-111">Können wir binden, klicken Sie dann die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> zu `BookTable` von der `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="1e7c2-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="1e7c2-112">`BookItemTemplate` ist die <xref:System.Windows.DataTemplate> , die definiert, wie die Daten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e7c2-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="1e7c2-113">`IntColorConverter` konvertiert `int` in eine Farbe.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="1e7c2-114">Mit der Verwendung dieses Konverters der <xref:System.Windows.Controls.TextBlock.Background%2A> Farbe des dritten <xref:System.Windows.Controls.TextBlock> grün wenn der Wert des `NumPages` andernfalls wird von höchstens 350 und Rot.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="1e7c2-115">Die Implementierung des Konverters wird hier nicht gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e7c2-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e7c2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e7c2-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="1e7c2-117">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="1e7c2-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="1e7c2-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1e7c2-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
