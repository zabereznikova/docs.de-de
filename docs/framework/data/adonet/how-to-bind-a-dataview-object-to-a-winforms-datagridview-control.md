---
title: 'Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: cf2a47c5d29c0af680ee4ccae503e92d3a9124d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194712"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="89273-102">Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="89273-102">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>

<span data-ttu-id="89273-103">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form.</span><span class="sxs-lookup"><span data-stu-id="89273-103">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="89273-104">Das <xref:System.Windows.Forms.DataGridView> unterstützt das Standard-Datenbindungsmodell von Windows Forms und ermöglicht so die Bindung an eine <xref:System.Data.DataView> und eine Vielzahl anderer Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="89273-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="89273-105">In den meisten Fällen dürfte jedoch eine Bindung an eine <xref:System.Windows.Forms.BindingSource>-Komponente erfolgen, die sich um die Details der Interaktion mit der Datenquelle kümmert.</span><span class="sxs-lookup"><span data-stu-id="89273-105">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="89273-106">Weitere Informationen zum- <xref:System.Windows.Forms.DataGridView> Steuerelement finden Sie unter Übersicht über das [DataGridView-Steuer](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms)Element.</span><span class="sxs-lookup"><span data-stu-id="89273-106">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="89273-107">So verbinden Sie ein "DataGridView"-Steuerelement mit einer "DataView"</span><span class="sxs-lookup"><span data-stu-id="89273-107">To connect a DataGridView control to a DataView</span></span>  
  
1. <span data-ttu-id="89273-108">Implementieren Sie eine Methode, mit der die Details des Abrufens von Daten aus einer Datenbank behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="89273-108">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="89273-109">Das folgende Codebeispiel implementiert eine `GetData`-Methode, die eine <xref:System.Data.SqlClient.SqlDataAdapter>-Komponente initialisiert, und verwendet diese, um ein <xref:System.Data.DataSet> aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="89273-109">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="89273-110">Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="89273-110">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="89273-111">Sie benötigen Zugriff auf einen Server, auf dem die SQL Server-AdventureWorks-Beispieldatenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="89273-111">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. <span data-ttu-id="89273-112">Binden Sie im <xref:System.Windows.Forms.Form.Load>-Ereignishandler Ihres Formulars das <xref:System.Windows.Forms.DataGridView>-Steuerelement an die <xref:System.Windows.Forms.BindingSource>-Komponente, und verwenden Sie die `GetData`-Methode, um Daten aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="89273-112">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="89273-113">Der <xref:System.Data.DataView> wird aus einer LINQ to DataSet Abfrage über den Kontakt erstellt <xref:System.Data.DataTable> und dann an die- <xref:System.Windows.Forms.BindingSource> Komponente gebunden.</span><span class="sxs-lookup"><span data-stu-id="89273-113">The <xref:System.Data.DataView> is created from a LINQ to DataSet query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="89273-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89273-114">See also</span></span>

- [<span data-ttu-id="89273-115">Datenbindung und LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="89273-115">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
