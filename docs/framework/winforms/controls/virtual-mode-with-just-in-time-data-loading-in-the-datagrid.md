---
title: 'Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Daten laden in das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 473b2ebab95c26d8df03efc9edf332c56fb7e0e0
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261673"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d71b1-102">Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Daten laden in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d71b1-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d71b1-103">Im folgenden Codebeispiel wird gezeigt, wie der virtuelle Modus im <xref:System.Windows.Forms.DataGridView>-Steuerelement mit einem Datencache verwendet wird, der nur bei Bedarf die Daten von einem Server lädt.</span><span class="sxs-lookup"><span data-stu-id="d71b1-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="d71b1-104">In diesem Beispiel wird ausführlich beschrieben [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="d71b1-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d71b1-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d71b1-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d71b1-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d71b1-106">Compiling the Code</span></span>  
 <span data-ttu-id="d71b1-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d71b1-107">This example requires:</span></span>  
  
-   <span data-ttu-id="d71b1-108">Verweise auf die Assemblys System, System.Data, System.XML und System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d71b1-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="d71b1-109">Zugriff auf einen Server mit der SQL Server-Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="d71b1-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="d71b1-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d71b1-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d71b1-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="d71b1-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d71b1-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d71b1-112">.NET Framework Security</span></span>  
 <span data-ttu-id="d71b1-113">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="d71b1-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d71b1-114">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="d71b1-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d71b1-115">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="d71b1-115">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71b1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d71b1-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [<span data-ttu-id="d71b1-117">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d71b1-117">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="d71b1-118">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d71b1-118">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d71b1-119">Virtueller Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d71b1-119">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
