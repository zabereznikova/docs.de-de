---
title: 'Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource ResetItem-Methode'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: eb97191e30cd2c4eb5ad8b8bbc158819ac1fe396
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261413"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="26508-102">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource ResetItem-Methode</span><span class="sxs-lookup"><span data-stu-id="26508-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="26508-103">Einige Datenquellen für Ihre Steuerelemente lösen keine Änderungsbenachrichtigungen aus, wenn Elemente geändert, hinzugefügt oder gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="26508-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="26508-104">Mit der <xref:System.Windows.Forms.BindingSource>-Komponente können Sie Bindungen zu solchen Datenquellen herstellen und Änderungsbenachrichtigungen in Ihrem Code auslösen.</span><span class="sxs-lookup"><span data-stu-id="26508-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26508-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26508-105">Example</span></span>  
 <span data-ttu-id="26508-106">Anhand dieses Formular wird gezeigt, wie Sie mit einer <xref:System.Windows.Forms.BindingSource>-Komponente eine Liste an ein <xref:System.Windows.Forms.DataGridView>-Steuerelement binden können.</span><span class="sxs-lookup"><span data-stu-id="26508-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="26508-107">Diese Liste löst keine Änderungsbenachrichtigungen aus, weshalb die <xref:System.Windows.Forms.BindingSource.ResetItem%2A>-Methode für die <xref:System.Windows.Forms.BindingSource> aufgerufen wird, wenn ein Element in der Liste ändert wurde.</span><span class="sxs-lookup"><span data-stu-id="26508-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="26508-108">sein.</span><span class="sxs-lookup"><span data-stu-id="26508-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="26508-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="26508-109">Compiling the Code</span></span>  
 <span data-ttu-id="26508-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="26508-110">This example requires:</span></span>  
  
-   <span data-ttu-id="26508-111">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="26508-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="26508-112">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="26508-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="26508-113">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="26508-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26508-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26508-114">See also</span></span>
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="26508-115">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="26508-115">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="26508-116">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="26508-116">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
