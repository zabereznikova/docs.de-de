---
title: 'Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04fee5f753cb4b3786d5ca58f85880f151caf0b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="9e4e7-102">Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e4e7-102">How to: Bind Data to the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9e4e7-103">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement unterstützt das Standard-Datenbindungsmodell von Windows Forms und ermöglicht so die Bindung an eine Vielzahl von Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to a variety of data sources.</span></span> <span data-ttu-id="9e4e7-104">In den meisten Fällen erfolgt jedoch eine Bindung an eine <xref:System.Windows.Forms.BindingSource>-Komponente, die die Details der Interaktion mit der Datenquelle verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-104">In most circumstances, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component which will manage the details of interacting with the data source.</span></span> <span data-ttu-id="9e4e7-105">Die <xref:System.Windows.Forms.BindingSource>-Komponente kann eine beliebige Windows Forms-Datenquelle darstellen und bietet Ihnen viel Flexibilität bei der Auswahl oder Änderung des Speicherorts Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-105">The <xref:System.Windows.Forms.BindingSource> component can represent any Windows Forms data source and gives you great flexibility when choosing or modifying the location of your data.</span></span> <span data-ttu-id="9e4e7-106">Weitere Informationen zu den Datenquellen, die von unterstützt die <xref:System.Windows.Forms.DataGridView> steuern, finden Sie unter [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9e4e7-106">For more information about the data sources supported by the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="9e4e7-107">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-107">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="9e4e7-108">Siehe auch [Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9e4e7-108">Also see [How to: Bind Data to the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="9e4e7-109">Prozedur</span><span class="sxs-lookup"><span data-stu-id="9e4e7-109">Procedure</span></span>  
  
#### <a name="to-connect-a-datagridview-control-to-data"></a><span data-ttu-id="9e4e7-110">So verbinden Sie ein DataGridView-Steuerelement mit Daten</span><span class="sxs-lookup"><span data-stu-id="9e4e7-110">To connect a DataGridView control to data</span></span>  
  
1.  <span data-ttu-id="9e4e7-111">Implementieren Sie eine Methode, mit der die Details des Abrufens von Daten aus einer Datenbank behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-111">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="9e4e7-112">Das folgende Codebeispiel implementiert eine `GetData`-Methode, die eine <xref:System.Data.SqlClient.SqlDataAdapter>-Komponente initialisiert, und verwendet diese, um ein <xref:System.Data.DataTable> mit Daten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9e4e7-113">Die <xref:System.Data.DataTable> wird dann an die <xref:System.Windows.Forms.BindingSource>-Komponente gebunden.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-113">The <xref:System.Data.DataTable> is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="9e4e7-114">Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-114">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="9e4e7-115">Sie benötigen Zugriff auf einen Server, auf dem die SQL Server-Beispieldatenbank "Northwind" installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-115">You will need access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  <span data-ttu-id="9e4e7-116">Binden Sie im <xref:System.Windows.Forms.Form.Load>-Ereignishandler Ihres Formulars das <xref:System.Windows.Forms.DataGridView>-Steuerelement an die <xref:System.Windows.Forms.BindingSource>-Komponente, und verwenden Sie die `GetData`-Methode, um Daten aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-116">In your form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9e4e7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e4e7-117">Example</span></span>  
 <span data-ttu-id="9e4e7-118">Das folgende vollständige Codebeispiel stellt Schaltflächen zum erneuten Laden von Daten aus der Datenbank und Übermitteln von Änderungen an die Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-118">The following complete code example provides buttons for reloading data from the database and submitting changes to the database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e4e7-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9e4e7-119">Compiling the Code</span></span>  
 <span data-ttu-id="9e4e7-120">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9e4e7-120">This example requires:</span></span>  
  
-   <span data-ttu-id="9e4e7-121">Verweise auf die Assemblys "System", "System.Windows.Forms", "System.Data" und "System.XML".</span><span class="sxs-lookup"><span data-stu-id="9e4e7-121">References to the System, System.Windows.Forms, System.Data, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="9e4e7-122">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9e4e7-122">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9e4e7-123">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-123">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="9e4e7-124">Siehe auch: [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9e4e7-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9e4e7-125">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9e4e7-125">.NET Framework Security</span></span>  
 <span data-ttu-id="9e4e7-126">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-126">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="9e4e7-127">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="9e4e7-127">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="9e4e7-128">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="9e4e7-128">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4e7-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e4e7-129">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="9e4e7-130">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e4e7-130">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="9e4e7-131">Protecting Connection Information (Schützen von Verbindungsinformationen)</span><span class="sxs-lookup"><span data-stu-id="9e4e7-131">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
