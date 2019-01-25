---
title: 'Vorgehensweise: Eine Windows Forms-Steuerelement ToolStripControlHost'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: 9069a86628afbde08c0166d7a04d5e325c0a7466
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698340"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="c6a03-102">Vorgehensweise: Eine Windows Forms-Steuerelement ToolStripControlHost</span><span class="sxs-lookup"><span data-stu-id="c6a03-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<span data-ttu-id="c6a03-103"><xref:System.Windows.Forms.ToolStripControlHost> dient zum Aktivieren des Hostings von beliebigen Windows Forms-Steuerelementen mithilfe des <xref:System.Windows.Forms.ToolStripControlHost>-Konstruktors oder durch die Erweiterung von <xref:System.Windows.Forms.ToolStripControlHost> selbst.</span><span class="sxs-lookup"><span data-stu-id="c6a03-103"><xref:System.Windows.Forms.ToolStripControlHost> is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="c6a03-104">Es ist einfacher, das Steuerelement durch Erweitern von <xref:System.Windows.Forms.ToolStripControlHost> und Implementieren der Eigenschaften und Methoden zu umschließen, die häufig verwendete Eigenschaften und Methoden des Steuerelements verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="c6a03-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="c6a03-105">Sie können Ereignisse für das Steuerelement auch auf der <xref:System.Windows.Forms.ToolStripControlHost>-Ebene verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="c6a03-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="c6a03-106">So hosten Sie ein Steuerelement in einem "ToolStripControlHost" durch Ableitung</span><span class="sxs-lookup"><span data-stu-id="c6a03-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1.  <span data-ttu-id="c6a03-107">Erweitern Sie <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="c6a03-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="c6a03-108">Implementieren Sie einen Standardkonstruktor, der einen Basisklassenkonstruktor aufruft, der das gewünschte Steuerelement übergibt.</span><span class="sxs-lookup"><span data-stu-id="c6a03-108">Implement a default constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2.  <span data-ttu-id="c6a03-109">Deklarieren Sie eine Eigenschaft mit demselben Typ wie für das umschlossene Steuerelement, und geben Sie `Control` als richtigen Typ des Steuerelements im Accessor der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="c6a03-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3.  <span data-ttu-id="c6a03-110">Machen Sie andere häufig verwendete Eigenschaften und Methoden des umschlossenen Steuerelements mithilfe von Eigenschaften und Methoden in der erweiterten Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6a03-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4.  <span data-ttu-id="c6a03-111">Überschreiben Sie optional die Methoden <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> und <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A>, und fügen Sie die bereitzustellenden Steuerelementereignisse hinzu.</span><span class="sxs-lookup"><span data-stu-id="c6a03-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5.  <span data-ttu-id="c6a03-112">Geben Sie die erforderlichen Wrapper für die Ereignisse an, die Sie verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="c6a03-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="c6a03-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6a03-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c6a03-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c6a03-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="c6a03-115">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c6a03-115">This example requires:</span></span>  
  
-   <span data-ttu-id="c6a03-116">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="c6a03-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c6a03-117">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c6a03-117">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c6a03-118">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="c6a03-118">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c6a03-119">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c6a03-119">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a03-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6a03-120">See also</span></span>
- <xref:System.Windows.Forms.ToolStripControlHost>
- [<span data-ttu-id="c6a03-121">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c6a03-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="c6a03-122">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="c6a03-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="c6a03-123">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="c6a03-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
