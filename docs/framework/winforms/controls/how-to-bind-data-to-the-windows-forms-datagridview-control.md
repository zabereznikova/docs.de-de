---
title: 'Vorgehensweise: Datenbindung in Windows Forms-DataGridView-Steuerelement'
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e147109a64687177f201ad1e312fab56ea61d604
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160069"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="88dfe-102">Vorgehensweise: Datenbindung in Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88dfe-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="88dfe-103">Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt die standardmäßige Windows Forms-Datenbindungsmodell verwendet, damit es mit einer Vielzahl von Datenquellen gebunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="88dfe-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="88dfe-104">In der Regel Sie binden an eine <xref:System.Windows.Forms.BindingSource> , verwaltet die Interaktion mit der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="88dfe-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="88dfe-105">Die <xref:System.Windows.Forms.BindingSource> kann jede beliebige Windows Forms-Datenquelle, die Ihnen viel Flexibilität bei der Auswahl oder Änderung des Daten Speicherorts bietet sein.</span><span class="sxs-lookup"><span data-stu-id="88dfe-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="88dfe-106">Weitere Informationen zu den Datenquellen der <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt, finden Sie die [Übersicht über das DataGridView-Steuerelement](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="88dfe-107">Visual Studio bietet umfassende Unterstützung für die Datenbindung an das DataGridView-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="88dfe-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="88dfe-108">Weitere Informationen finden Sie unter [Vorgehensweise: Binden von Daten an das Windows Forms-DataGridView-Steuerelement, das mithilfe des Designers](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="88dfe-109">So verbinden ein DataGridView-Steuerelement mit Daten:</span><span class="sxs-lookup"><span data-stu-id="88dfe-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="88dfe-110">Implementieren Sie eine Methode, um die Details zum Abrufen der Daten zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="88dfe-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="88dfe-111">Das folgende Codebeispiel implementiert eine `GetData` -Methode, initialisiert ein <xref:System.Data.SqlClient.SqlDataAdapter>, und verwendet ihn zum Auffüllen einer <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="88dfe-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="88dfe-112">Klicken Sie dann bindet die <xref:System.Data.DataTable> auf die <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="88dfe-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="88dfe-113">Des Formulars <xref:System.Windows.Forms.Form.Load> Ereignishandler, binden die <xref:System.Windows.Forms.DataGridView> die Steuerung an die <xref:System.Windows.Forms.BindingSource>, und rufen Sie die `GetData` Methode zum Abrufen der Daten.</span><span class="sxs-lookup"><span data-stu-id="88dfe-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="88dfe-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88dfe-114">Example</span></span>

<span data-ttu-id="88dfe-115">Dieser vollständige Codebeispiel ruft Daten ab, aus einer Datenbank in einem DataGridView-Steuerelement in einem Windows-Formular zu füllen.</span><span class="sxs-lookup"><span data-stu-id="88dfe-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="88dfe-116">Das Formular verfügt auch über die Schaltflächen zum Laden von Daten und Übermitteln von Änderungen an der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="88dfe-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="88dfe-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="88dfe-117">This example requires:</span></span> 

- <span data-ttu-id="88dfe-118">Zugriff mit der Beispieldatenbank Northwind-SQL Server.</span><span class="sxs-lookup"><span data-stu-id="88dfe-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="88dfe-119">Weitere Informationen zum Installieren der Beispieldatenbank Northwind finden Sie unter [erhalten Sie die Beispieldatenbanken ADO.NET Codebeispiele](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="88dfe-120">Verweise auf die Assemblys System, "System.Windows.Forms", "System.Data" und "System.xml".</span><span class="sxs-lookup"><span data-stu-id="88dfe-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="88dfe-121">Fügen Sie zum Erstellen und dieses Beispiel ausführen, die den Code in die *Form1* Codedatei in einem neuen Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="88dfe-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="88dfe-122">Informationen zum Erstellen von der C# oder Visual Basic über die Befehlszeile, finden Sie unter [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="88dfe-123">Füllen Sie die `connectionString` Variable im Beispiel durch die Werte für Ihre Beispieldatenbank Northwind-SQL Server-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="88dfe-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="88dfe-124">Windows-Authentifizierung, integrierte Sicherheit, so genannte ist eine sicherere Methode für die Verbindung mit der Datenbank als ein Kennwort in der Verbindungszeichenfolge speichern.</span><span class="sxs-lookup"><span data-stu-id="88dfe-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="88dfe-125">Weitere Informationen zur verbindungssicherheit finden Sie unter [Schützen von Verbindungsinformationen](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="88dfe-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88dfe-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="88dfe-127">Anzeigen von Daten in Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88dfe-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="88dfe-128">Schützen von Verbindungsinformationen</span><span class="sxs-lookup"><span data-stu-id="88dfe-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
