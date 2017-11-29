---
title: 'Gewusst wie: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt'
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
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21623987e9e3798488df6ed0e001a2baf54c3575
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="fc8df-102">Gewusst wie: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt</span><span class="sxs-lookup"><span data-stu-id="fc8df-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="fc8df-103">Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an ein Objekt oder eine Methode zu binden, das bzw. die andere Objekte generiert.</span><span class="sxs-lookup"><span data-stu-id="fc8df-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="fc8df-104">Diese Art von Objekt oder Methode wird als Factory bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fc8df-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="fc8df-105">Die Datenquelle kann beispielsweise der Rückgabewert aus einem Methodenaufruf anstelle eines Objekts im Arbeitsspeicher oder eines Typs sein.</span><span class="sxs-lookup"><span data-stu-id="fc8df-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="fc8df-106">Sie können ein Steuerelement an diese Art von Datenquelle binden, solange die Quelle eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fc8df-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="fc8df-107">Sie können ein Steuerelement problemlos an ein Factoryobjekt binden, indem Sie das <xref:System.Windows.Forms.BindingSource>-Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc8df-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc8df-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc8df-108">Example</span></span>  
 <span data-ttu-id="fc8df-109">Das folgende Beispiel zeigt, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mithilfe eines <xref:System.Windows.Forms.BindingSource>-Steuerelements an eine Factorymethode gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="fc8df-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="fc8df-110">Die Factorymethode lautet `GetOrdersByCustomerId` und gibt alle Befehle für einen bestimmten Kunden in der Northwind-Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="fc8df-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc8df-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fc8df-111">Compiling the Code</span></span>  
 <span data-ttu-id="fc8df-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fc8df-112">This example requires:</span></span>  
  
-   <span data-ttu-id="fc8df-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="fc8df-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fc8df-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fc8df-114">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fc8df-115">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="fc8df-115">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="fc8df-116">Siehe auch: [Vorgehensweise: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fc8df-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8df-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc8df-117">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="fc8df-118">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="fc8df-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="fc8df-119">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="fc8df-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
