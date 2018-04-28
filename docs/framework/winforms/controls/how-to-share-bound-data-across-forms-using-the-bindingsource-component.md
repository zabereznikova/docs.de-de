---
title: 'Gewusst wie: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente'
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
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1907f25e2d9bfe5fc6e93020add47d8a52379e87
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="d263f-102">Gewusst wie: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="d263f-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="d263f-103">Sie können Daten einfach in mehreren Formularen gemeinsam nutzen (freigeben), indem Sie die <xref:System.Windows.Forms.BindingSource>-Komponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="d263f-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="d263f-104">Beispielsweise könnte es sein, dass Sie ein schreibgeschütztes Formular, in dem die Datenquellendaten zusammengefasst werden, sowie ein bearbeitbares Formular anzeigen möchten, das detaillierte Informationen über das Element enthält, das momentan in der Datenquelle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d263f-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="d263f-105">In diesem Beispiel wird dieses Szenario veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d263f-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d263f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d263f-106">Example</span></span>  
 <span data-ttu-id="d263f-107">Im folgenden Codebeispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.BindingSource> und die an sie gebundenen Daten in mehreren Formularen gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="d263f-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="d263f-108">In diesem Beispiel wird die gemeinsam genutzte <xref:System.Windows.Forms.BindingSource> an den Konstruktor des untergeordneten Formulars übergeben.</span><span class="sxs-lookup"><span data-stu-id="d263f-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="d263f-109">Das untergeordnete Formular ermöglicht es dem Benutzer, die Daten für das aktuell ausgewählte Element im Hauptformular zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="d263f-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d263f-110">Das <xref:System.Windows.Forms.BindingSource.BindingComplete>-Ereignis für die <xref:System.Windows.Forms.BindingSource>-Komponente wird in diesem Beispiel, um sicherzustellen, dass die beiden Formulare synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="d263f-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="d263f-111">Weitere Informationen dazu, warum dies geschieht, finden Sie unter [Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span><span class="sxs-lookup"><span data-stu-id="d263f-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d263f-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d263f-112">Compiling the Code</span></span>  
 <span data-ttu-id="d263f-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d263f-113">This example requires:</span></span>  
  
-   <span data-ttu-id="d263f-114">Verweise auf die Assemblys "System", "System.Windows.Forms", "System.Drawing", "System.Data" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="d263f-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="d263f-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d263f-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d263f-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="d263f-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="d263f-117">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d263f-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d263f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d263f-118">See Also</span></span>  
 [<span data-ttu-id="d263f-119">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="d263f-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="d263f-120">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="d263f-120">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="d263f-121">Vorgehensweise: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="d263f-121">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
