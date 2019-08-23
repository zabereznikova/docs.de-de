---
title: 'Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960433"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="29384-102">Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29384-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="29384-103">Mithilfe der <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Sort%2A> -Eigenschaft und der- <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft können Sie die Sortier-und Filterfunktion des Steuer Elements verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="29384-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="29384-104">Sie können eine einfache Sortierung anwenden, wenn die zugrunde liegende Daten <xref:System.ComponentModel.IBindingList>Quelle eine ist, und Sie können Filter und erweiterte Sortierung anwenden, wenn die <xref:System.ComponentModel.IBindingListView>Datenquelle eine ist.</span><span class="sxs-lookup"><span data-stu-id="29384-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="29384-105">Die <xref:System.Windows.Forms.BindingSource.Sort%2A> -Eigenschaft erfordert die ADO.NET-Standard Syntax: eine Zeichenfolge, die den Namen einer Datenspalte in der Daten `ASC` Quelle `DESC` darstellt, gefolgt von oder, um anzugeben, ob die Liste in aufsteigender oder absteigender Reihenfolge sortiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="29384-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="29384-106">Sie können eine erweiterte Sortierung oder eine Sortierung mit mehreren Spalten festlegen, indem Sie jede Spalte durch ein Komma Trennzeichen trennen.</span><span class="sxs-lookup"><span data-stu-id="29384-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="29384-107">Die <xref:System.Windows.Forms.BindingSource.Filter%2A> -Eigenschaft nimmt einen Zeichen folgen Ausdruck an.</span><span class="sxs-lookup"><span data-stu-id="29384-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29384-108">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="29384-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="29384-109">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="29384-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="29384-110">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="29384-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="29384-111">So filtern Sie Daten mit der BindingSource</span><span class="sxs-lookup"><span data-stu-id="29384-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="29384-112">Legen Sie <xref:System.Windows.Forms.BindingSource.Filter%2A> die-Eigenschaft auf den gewünschten Ausdruck fest.</span><span class="sxs-lookup"><span data-stu-id="29384-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="29384-113">Im folgenden Codebeispiel ist der Ausdruck ein Spaltenname, gefolgt von dem Wert, den Sie für die Spalte benötigen.</span><span class="sxs-lookup"><span data-stu-id="29384-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="29384-114">So sortieren Sie Daten mit der BindingSource</span><span class="sxs-lookup"><span data-stu-id="29384-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="29384-115">Legen Sie <xref:System.Windows.Forms.BindingSource.Sort%2A> die-Eigenschaft auf den Spaltennamen fest, den `ASC` Sie `DESC` folgen möchten, oder, um den aufsteigenden oder absteigenden Auftrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29384-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="29384-116">Trennen Sie mehrere Spalten durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="29384-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="29384-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29384-117">Example</span></span>  
 <span data-ttu-id="29384-118">Im folgenden Codebeispiel werden Daten aus der Customers-Tabelle der Beispieldatenbank Northwind in ein <xref:System.Windows.Forms.DataGridView> -Steuerelement geladen, und die angezeigten Daten werden gefiltert und sortiert.</span><span class="sxs-lookup"><span data-stu-id="29384-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29384-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="29384-119">Compiling the Code</span></span>  
 <span data-ttu-id="29384-120">Um dieses Beispiel auszuführen, fügen Sie den Code in ein Formular ein, <xref:System.Windows.Forms.BindingSource> das `BindingSource1` ein mit <xref:System.Windows.Forms.DataGridView> dem `dataGridView1`Namen und ein mit dem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="29384-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="29384-121">Behandeln Sie <xref:System.Windows.Forms.Form.Load> das-Ereignis für das Formular `InitializeSortedFilteredBindingSource` , und nennen Sie es in der Load-Ereignishandlermethode</span><span class="sxs-lookup"><span data-stu-id="29384-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29384-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29384-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="29384-123">[Vorgehensweise: Installieren von Beispiel Datenbanken](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="29384-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="29384-124">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="29384-124">BindingSource Component</span></span>](bindingsource-component.md)
