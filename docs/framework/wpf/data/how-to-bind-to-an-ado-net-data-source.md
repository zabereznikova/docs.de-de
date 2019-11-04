---
title: 'Gewusst wie: Binden an eine ADO.NET-Datenquelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 0b3d7147f45bee5e8abd95bdc51c5f5f695cf830
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458407"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="2bc07-102">Gewusst wie: Binden an eine ADO.NET-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="2bc07-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="2bc07-103">In diesem Beispiel wird gezeigt, wie ein [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox>-Steuerelement an eine ADO.net-`DataSet`gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="2bc07-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="2bc07-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bc07-104">Example</span></span>

<span data-ttu-id="2bc07-105">In diesem Beispiel wird ein `OleDbConnection`-Objekt zum Herstellen der Verbindung mit der Datenquelle verwendet, die als `Access MDB`-Datei in der Verbindungszeichenfolge angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2bc07-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="2bc07-106">Nach dem Herstellen der Verbindung wird ein `OleDbDataAdapter`-Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="2bc07-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="2bc07-107">Das `OleDbDataAdapter`-Objekt führt eine SELECT strukturierte Abfragesprache (SQL)-Anweisung aus, um das Recordset aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2bc07-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="2bc07-108">Die Ergebnisse des SQL-Befehls werden in einer `DataTable` der `DataSet` gespeichert, indem die `Fill`-Methode der `OleDbDataAdapter`aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2bc07-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="2bc07-109">Die `DataTable` in diesem Beispiel heißt `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="2bc07-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="2bc07-110">Im Beispiel wird dann die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> auf das `DataSet`-Objekt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2bc07-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="2bc07-111">Anschließend können Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> an `BookTable` der `DataSet`binden:</span><span class="sxs-lookup"><span data-stu-id="2bc07-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="2bc07-112">`BookItemTemplate` ist der <xref:System.Windows.DataTemplate>, der definiert, wie die Daten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="2bc07-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="2bc07-113">`IntColorConverter` konvertiert `int` in eine Farbe.</span><span class="sxs-lookup"><span data-stu-id="2bc07-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="2bc07-114">Bei Verwendung dieses Konverters wird die <xref:System.Windows.Controls.TextBlock.Background%2A> Farbe der dritten <xref:System.Windows.Controls.TextBlock> grün angezeigt, wenn der Wert von `NumPages` kleiner als 350 und andernfalls rot ist.</span><span class="sxs-lookup"><span data-stu-id="2bc07-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="2bc07-115">Die Implementierung des Konverters wird hier nicht gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bc07-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bc07-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bc07-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="2bc07-117">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="2bc07-117">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="2bc07-118">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2bc07-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
