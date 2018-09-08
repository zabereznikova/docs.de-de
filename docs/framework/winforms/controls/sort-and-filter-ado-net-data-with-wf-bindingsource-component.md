---
title: 'Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms'
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
ms.openlocfilehash: 932d30d356225d88d7ef149561cc4c5cc8ac4dd0
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44067937"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="c082c-102">Gewusst wie: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c082c-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="c082c-103">Sie können das Sortieren und Filtern von Funktion verfügbar machen <xref:System.Windows.Forms.BindingSource> steuern, über die <xref:System.Windows.Forms.BindingSource.Sort%2A> und <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c082c-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="c082c-104">Sie können anwenden, einfache Sortierung, wenn die zugrunde liegende Datenquelle ist ein <xref:System.ComponentModel.IBindingList>, und Sie können Filter anwenden und erweiterte Sortierung, wenn die Datenquelle ist ein <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="c082c-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="c082c-105">Die <xref:System.Windows.Forms.BindingSource.Sort%2A> Eigenschaft ist erforderlich, Standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Syntax: eine Zeichenfolge, die den Namen einer Spalte mit Daten in der Datenquelle darstellt, gefolgt von `ASC` oder `DESC` an, ob die Liste in aufsteigender oder absteigender Reihenfolge sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c082c-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="c082c-106">Sie können erweiterte Sortierung oder mehrere Spalten zu sortieren, nach jeder Spalte durch ein Komma als Trennzeichen trennen festlegen.</span><span class="sxs-lookup"><span data-stu-id="c082c-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="c082c-107">Die <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft akzeptiert einen Zeichenfolgenausdruck.</span><span class="sxs-lookup"><span data-stu-id="c082c-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c082c-108">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="c082c-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="c082c-109">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="c082c-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="c082c-110">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="c082c-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="c082c-111">Zum Filtern von Daten mithilfe der BindingSource</span><span class="sxs-lookup"><span data-stu-id="c082c-111">To filter data with the BindingSource</span></span>  
  
-   <span data-ttu-id="c082c-112">Legen Sie die <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft, um den Ausdruck ein, Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="c082c-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="c082c-113">Das folgende Codebeispiel zeigt ist der Ausdruck einen Spaltennamen, gefolgt von dem Wert, der für die Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="c082c-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="c082c-114">So sortieren Sie Daten mithilfe der BindingSource</span><span class="sxs-lookup"><span data-stu-id="c082c-114">To sort data with the BindingSource</span></span>  
  
1.  <span data-ttu-id="c082c-115">Legen Sie die <xref:System.Windows.Forms.BindingSource.Sort%2A> Eigenschaft auf den gewünschten gefolgt von Spaltennamen `ASC` oder `DESC` die aufsteigende oder absteigende Reihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="c082c-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2.  <span data-ttu-id="c082c-116">Trennen Sie mehrere Spalten durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="c082c-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="c082c-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c082c-117">Example</span></span>  
 <span data-ttu-id="c082c-118">Das folgende Codebeispiel lädt Daten aus der Customers-Tabelle der Northwind-Beispieldatenbank in einer <xref:System.Windows.Forms.DataGridView> zu steuern, gefiltert und sortiert die angezeigten Daten.</span><span class="sxs-lookup"><span data-stu-id="c082c-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c082c-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c082c-119">Compiling the Code</span></span>  
 <span data-ttu-id="c082c-120">Um dieses Beispiel auszuführen, fügen Sie den Code in ein Formular enthält ein <xref:System.Windows.Forms.BindingSource> mit dem Namen `BindingSource1` und <xref:System.Windows.Forms.DataGridView> mit dem Namen `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="c082c-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="c082c-121">Behandeln der <xref:System.Windows.Forms.Form.Load> -Ereignis für das Formular, und rufen `InitializeSortedFilteredBindingSource` in die Load-Ereignishandlermethode.</span><span class="sxs-lookup"><span data-stu-id="c082c-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c082c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c082c-122">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [<span data-ttu-id="c082c-123">Gewusst wie: Installieren von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="c082c-123">How to: Install Sample Databases</span></span>](https://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [<span data-ttu-id="c082c-124">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="c082c-124">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
