---
title: 'Vorgehensweise: Kennzeichnen von Datenquellenaktualisierungen in einem Windows Forms-Steuerelement mithilfe der BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: 16dbe4da1efecd120d4da4d66c3d79ec907b92a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218646"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="688b6-102">Vorgehensweise: Kennzeichnen von Datenquellenaktualisierungen in einem Windows Forms-Steuerelement mithilfe der BindingSource</span><span class="sxs-lookup"><span data-stu-id="688b6-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="688b6-103">Wenn Sie an Daten gebundene Steuerelemente verwenden, müssen Sie manchmal auf Änderungen in der Datenquelle reagieren, wenn die Datenquelle keine Ereignisse für Listenänderungen auslöst.</span><span class="sxs-lookup"><span data-stu-id="688b6-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="688b6-104">Wenn Sie die <xref:System.Windows.Forms.BindingSource> Komponente zum Binden Ihrer Datenquelle an ein Windows Forms-Steuerelement verwenden, können Sie das Steuerelement benachrichtigen, dass sich Ihre Datenquelle geändert hat, indem Sie die Methode <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="688b6-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="688b6-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="688b6-105">Example</span></span>  
 <span data-ttu-id="688b6-106">Das folgende Codebeispiel veranschaulicht die Verwendung der Methode <xref:System.Windows.Forms.BindingSource.ResetBindings%2A>, um ein gebundenes Steuerelement über eine Aktualisierung in der Datenquelle zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="688b6-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="688b6-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="688b6-107">Compiling the Code</span></span>  
 <span data-ttu-id="688b6-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="688b6-108">This example requires:</span></span>  
  
-   <span data-ttu-id="688b6-109">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="688b6-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="688b6-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="688b6-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="688b6-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="688b6-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688b6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="688b6-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="688b6-113">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="688b6-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="688b6-114">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="688b6-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
