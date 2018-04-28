---
title: 'Gewusst wie: Navigieren durch ein DataSet mithilfe des BindingNavigator-Steuerelements in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2088866b34e9ef96781711609e084c4f53b57b5e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="e0fa2-102">Gewusst wie: Navigieren durch ein DataSet mithilfe des BindingNavigator-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0fa2-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="e0fa2-103">Wenn Sie datengesteuerte Anwendungen erstellen, müssen Sie oft Auflistungen von Daten für Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="e0fa2-104">Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement in Verbindung mit der <xref:System.Windows.Forms.BindingSource>-Komponente stellt eine bequeme und erweiterbare Lösung bereit, um eine Auflistung zu durchlaufen und Elemente nacheinander anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0fa2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0fa2-105">Example</span></span>  
 <span data-ttu-id="e0fa2-106">Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Forms.BindingNavigator>-Steuerelement verwenden, um Daten zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="e0fa2-107">Das Dataset befindet sich in <xref:System.Data.DataView>, die an ein <xref:System.Windows.Forms.TextBox>-Steuerelement mit einer <xref:System.Windows.Forms.BindingSource>-Komponente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0fa2-108">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="e0fa2-109">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="e0fa2-110">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="e0fa2-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0fa2-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e0fa2-111">Compiling the Code</span></span>  
 <span data-ttu-id="e0fa2-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e0fa2-112">This example requires:</span></span>  
  
-   <span data-ttu-id="e0fa2-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing", "System.Windows.Forms" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="e0fa2-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="e0fa2-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e0fa2-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e0fa2-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="e0fa2-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e0fa2-116">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e0fa2-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0fa2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0fa2-117">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="e0fa2-118">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e0fa2-118">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="e0fa2-119">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="e0fa2-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="e0fa2-120">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="e0fa2-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
