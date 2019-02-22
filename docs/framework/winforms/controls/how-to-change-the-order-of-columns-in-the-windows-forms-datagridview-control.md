---
title: 'Vorgehensweise: Ändern Sie die Reihenfolge der Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: a8e18080e757ceb4818bb795926a1eb4c27cf067
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583354"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="72717-102">Vorgehensweise: Ändern Sie die Reihenfolge der Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72717-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="72717-103">Wenn Sie eine <xref:System.Windows.Forms.DataGridView> verwenden, um Daten aus einer Datenquelle anzuzeigen, werden die Spalten im Schema der Datenquelle manchmal nicht in der von Ihnen gewünschten Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72717-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="72717-104">Sie können die Reihenfolge, in der die Spalten angezeigt werden, durch Verwenden der <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridViewColumn>-Klasse ändern.</span><span class="sxs-lookup"><span data-stu-id="72717-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="72717-105">Im folgenden Codebeispiel werden einige der Spalten neu angeordnet, die automatisch generiert werden, wenn Sie eine Bindung zur Customers-Tabelle in der Beispieldatenbank Northwind herstellen.</span><span class="sxs-lookup"><span data-stu-id="72717-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="72717-106">Weitere Informationen über das Binden der <xref:System.Windows.Forms.DataGridView> in einer Datenbanktabelle zu steuern, finden Sie unter [Vorgehensweise: Binden von Daten an die Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="72717-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="72717-107">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="72717-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="72717-108">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Ändern der Reihenfolge der Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="72717-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72717-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72717-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72717-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="72717-110">Compiling the Code</span></span>  
 <span data-ttu-id="72717-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="72717-111">This example requires:</span></span>  
  
-   <span data-ttu-id="72717-112">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `customersDataGridView`, das an eine Tabelle mit den angegebenen Spaltennamen gebunden ist, beispielsweise die `Customers`-Tabelle in der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="72717-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="72717-113">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> und <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72717-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72717-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72717-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="72717-115">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72717-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="72717-116">Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72717-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)
