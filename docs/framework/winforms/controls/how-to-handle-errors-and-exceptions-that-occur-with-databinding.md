---
title: 'Gewusst wie: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung'
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
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a78612fc17eea01508dcba9247ece68be2e19a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="593de-102">Gewusst wie: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="593de-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="593de-103">Häufig treten Ausnahmen und Fehler bei den zugrunde liegenden Geschäftsobjekten auf, wenn Sie diese an Steuerelemente binden.</span><span class="sxs-lookup"><span data-stu-id="593de-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="593de-104">Sie können diese Fehler und Ausnahmen abfangen und dann wiederherstellen oder die Fehlerinformationen an den Benutzer übergeben, indem Sie das <xref:System.Windows.Forms.Binding.BindingComplete>-Ereignis für eine bestimmte <xref:System.Windows.Forms.Binding>-, <xref:System.Windows.Forms.BindingSource>- oder <xref:System.Windows.Forms.CurrencyManager>-Komponente behandeln.</span><span class="sxs-lookup"><span data-stu-id="593de-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="593de-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="593de-105">Example</span></span>  
 <span data-ttu-id="593de-106">In diesem Codebeispiel wird das Behandeln von Fehlern und Ausnahmen veranschaulicht, die während der Datenbindung auftreten.</span><span class="sxs-lookup"><span data-stu-id="593de-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="593de-107">Es zeigt das Abfangen von Fehlern, indem das <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>-Ereignis der <xref:System.Windows.Forms.Binding>Objekte behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="593de-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="593de-108">Um Fehler und Ausnahmen durch die Behandlung dieses Ereignisses abfangen zu können, müssen Sie die Formatierung für die Bindung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="593de-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="593de-109">Sie können die Formatierung beim Erstellen der Bindung oder beim Hinzufügen zur Bindungsauflistung oder beim Festlegen der <xref:System.Windows.Forms.Binding.FormattingEnabled%2A>-Eigenschaft auf `true` aktivieren.</span><span class="sxs-lookup"><span data-stu-id="593de-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="593de-110">Wenn der Code ausgeführt und eine leere Zeichenfolge für den Namen des Teils oder ein Wert für die Teilenummer eingegeben wird, der kleiner als 100 ist, wird ein Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="593de-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="593de-111">Dies ist ein Ergebnis der Behandlung des <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>-Ereignisses für diese Textfeldbindungen.</span><span class="sxs-lookup"><span data-stu-id="593de-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="593de-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="593de-112">Compiling the Code</span></span>  
 <span data-ttu-id="593de-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="593de-113">This example requires:</span></span>  
  
-   <span data-ttu-id="593de-114">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="593de-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="593de-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="593de-115">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="593de-116">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="593de-116">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="593de-117">Siehe auch: [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="593de-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593de-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="593de-118">See Also</span></span>  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>  
 [<span data-ttu-id="593de-119">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="593de-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
