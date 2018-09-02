---
title: 'Gewusst wie: Anpassen der Hinzufügung von Elementen mithilfe der BindingSource von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: f8956ceb8da2aa14aea8b7e62b9d60ab656a3891
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405214"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="06168-102">Gewusst wie: Anpassen der Hinzufügung von Elementen mithilfe der BindingSource von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06168-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="06168-103">Wenn Sie eine <xref:System.Windows.Forms.BindingSource> -Komponente zum Binden eines Windows Forms-Steuerelements an eine Datenquelle verwenden, kann es ggf. erforderlich sein, die Erstellung neuer Elemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="06168-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="06168-104">Die <xref:System.Windows.Forms.BindingSource> -Komponente vereinfacht dies durch die Bereitstellung des <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignisses, das in der Regel ausgelöst wird, wenn das gebundene Steuerelement ein neues Element erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="06168-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="06168-105">Ihr Ereignishandler kann jedes erforderliche benutzerdefinierte Verhalten (z. B. das Aufrufen einer Methode für einen Webdienst oder das Abrufen eines neuen Objekts aus einer Klassenfactory) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06168-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06168-106">Wenn ein Element durch Verarbeiten des <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignisses hinzugefügt wird, kann die Hinzufügung nicht abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="06168-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06168-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06168-107">Example</span></span>  
 <span data-ttu-id="06168-108">Das folgende Beispiel zeigt, wie ein <xref:System.Windows.Forms.DataGridView> -Steuerelement mithilfe einer <xref:System.Windows.Forms.BindingSource> -Komponente an eine Klassenfactory gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="06168-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="06168-109">Wenn der Benutzer auf die neue Zeile des <xref:System.Windows.Forms.DataGridView> -Steuerelements klickt, wird das <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="06168-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="06168-110">Der Ereignishandler erstellt ein neues `DemoCustomer`-Objekt, das der Eigenschaft <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="06168-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="06168-111">Dies bewirkt, dass das neue `DemoCustomer` -Objekt der Liste der <xref:System.Windows.Forms.BindingSource> -Komponente hinzugefügt und in der neuen Zeile des <xref:System.Windows.Forms.DataGridView> -Steuerelements angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="06168-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="06168-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="06168-112">Compiling the Code</span></span>  
 <span data-ttu-id="06168-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="06168-113">This example requires:</span></span>  
  
-   <span data-ttu-id="06168-114">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="06168-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="06168-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="06168-115">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="06168-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="06168-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="06168-117">Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="06168-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06168-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06168-118">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="06168-119">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="06168-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="06168-120">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="06168-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
