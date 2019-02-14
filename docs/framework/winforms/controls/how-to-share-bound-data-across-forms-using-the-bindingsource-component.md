---
title: 'Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 6631fb4c4483853b3c4ba6c2e3484654c4f83342
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260841"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="373a9-102">Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="373a9-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="373a9-103">Sie können Daten einfach in mehreren Formularen gemeinsam nutzen (freigeben), indem Sie die <xref:System.Windows.Forms.BindingSource>-Komponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="373a9-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="373a9-104">Beispielsweise könnte es sein, dass Sie ein schreibgeschütztes Formular, in dem die Datenquellendaten zusammengefasst werden, sowie ein bearbeitbares Formular anzeigen möchten, das detaillierte Informationen über das Element enthält, das momentan in der Datenquelle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="373a9-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="373a9-105">In diesem Beispiel wird dieses Szenario veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="373a9-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="373a9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="373a9-106">Example</span></span>  
 <span data-ttu-id="373a9-107">Im folgenden Codebeispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.BindingSource> und die an sie gebundenen Daten in mehreren Formularen gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="373a9-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="373a9-108">In diesem Beispiel wird die gemeinsam genutzte <xref:System.Windows.Forms.BindingSource> an den Konstruktor des untergeordneten Formulars übergeben.</span><span class="sxs-lookup"><span data-stu-id="373a9-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="373a9-109">Das untergeordnete Formular ermöglicht es dem Benutzer, die Daten für das aktuell ausgewählte Element im Hauptformular zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="373a9-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="373a9-110">Das <xref:System.Windows.Forms.BindingSource.BindingComplete>-Ereignis für die <xref:System.Windows.Forms.BindingSource>-Komponente wird in diesem Beispiel, um sicherzustellen, dass die beiden Formulare synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="373a9-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="373a9-111">Weitere Informationen dazu, warum dies geschieht, finden Sie unter [Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span><span class="sxs-lookup"><span data-stu-id="373a9-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="373a9-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="373a9-112">Compiling the Code</span></span>  
 <span data-ttu-id="373a9-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="373a9-113">This example requires:</span></span>  
  
-   <span data-ttu-id="373a9-114">Verweise auf die Assemblys "System", "System.Windows.Forms", "System.Drawing", "System.Data" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="373a9-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="373a9-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="373a9-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="373a9-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="373a9-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373a9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="373a9-117">See also</span></span>
- [<span data-ttu-id="373a9-118">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="373a9-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="373a9-119">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="373a9-119">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="373a9-120">Vorgehensweise: Behandeln von Fehlern und Ausnahmen, die auftreten, mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="373a9-120">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
