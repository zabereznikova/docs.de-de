---
title: 'Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 3a3089073cdc5afb4ee51caca9114b401c740b45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795004"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="ebbd1-102">Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ebbd1-102">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ebbd1-103">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-103">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="ebbd1-104">Das <xref:System.Windows.Forms.DataGridView> unterstützt das Standard-Datenbindungsmodell von Windows Forms und ermöglicht so die Bindung an eine <xref:System.Data.DataView> und eine Vielzahl anderer Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="ebbd1-105">In den meisten Fällen dürfte jedoch eine Bindung an eine <xref:System.Windows.Forms.BindingSource>-Komponente erfolgen, die sich um die Details der Interaktion mit der Datenquelle kümmert.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-105">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="ebbd1-106">Weitere Informationen zum-Steuer <xref:System.Windows.Forms.DataGridView> Element finden Sie unter Übersicht über das [DataGridView-Steuer](../../winforms/controls/datagridview-control-overview-windows-forms.md)Element.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-106">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="ebbd1-107">So verbinden Sie ein "DataGridView"-Steuerelement mit einer "DataView"</span><span class="sxs-lookup"><span data-stu-id="ebbd1-107">To connect a DataGridView control to a DataView</span></span>  
  
1. <span data-ttu-id="ebbd1-108">Implementieren Sie eine Methode, mit der die Details des Abrufens von Daten aus einer Datenbank behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-108">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="ebbd1-109">Das folgende Codebeispiel implementiert eine `GetData`-Methode, die eine <xref:System.Data.SqlClient.SqlDataAdapter>-Komponente initialisiert, und verwendet diese, um ein <xref:System.Data.DataSet> aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-109">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ebbd1-110">Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-110">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="ebbd1-111">Sie benötigen Zugriff auf einen Server, auf dem die SQL Server-AdventureWorks-Beispieldatenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-111">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. <span data-ttu-id="ebbd1-112">Binden Sie im <xref:System.Windows.Forms.Form.Load>-Ereignishandler Ihres Formulars das <xref:System.Windows.Forms.DataGridView>-Steuerelement an die <xref:System.Windows.Forms.BindingSource>-Komponente, und verwenden Sie die `GetData`-Methode, um Daten aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-112">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="ebbd1-113">Der <xref:System.Data.DataView> wird aus einer LINQ to DataSet Abfrage über den Kontakt <xref:System.Data.DataTable> erstellt und dann an die <xref:System.Windows.Forms.BindingSource> -Komponente gebunden.</span><span class="sxs-lookup"><span data-stu-id="ebbd1-113">The <xref:System.Data.DataView> is created from a LINQ to DataSet query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="ebbd1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebbd1-114">See also</span></span>

- [<span data-ttu-id="ebbd1-115">Datenbindung und LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ebbd1-115">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
