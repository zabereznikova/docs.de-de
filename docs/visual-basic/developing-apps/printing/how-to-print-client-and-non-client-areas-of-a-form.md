---
title: 'Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- title bar [Visual Basic], printing
- printing
- borders [Visual Basic], printing
- entire form
- non-client area [Visual Basic], printing
ms.assetid: 856bb0e4-dbc3-47e2-81cd-4b376cf07757
ms.openlocfilehash: 5109993146a8d53d5cbeebcc52c018a6f0f57ed5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408438"
---
# <a name="how-to-print-client-and-non-client-areas-of-a-form-visual-basic"></a><span data-ttu-id="d60f6-102">Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d60f6-102">How to: Print Client and Non-Client Areas of a Form (Visual Basic)</span></span>
<span data-ttu-id="d60f6-103">Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie schnell ein Bild eines Formulars genau so drucken, wie es auf dem Bildschirm angezeigt wird, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d60f6-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="d60f6-104">Die folgende Vorgehensweise zeigt das Drucken eines Formulars, einschließlich des Clientbereichs und des Nicht-Clientbereichs.</span><span class="sxs-lookup"><span data-stu-id="d60f6-104">The following procedure shows how to print a form, including both the client area and the non-client area.</span></span> <span data-ttu-id="d60f6-105">Der Nicht-Clientbereich beinhaltet die Titelleiste, Rahmen und Scrollleisten.</span><span class="sxs-lookup"><span data-stu-id="d60f6-105">The non-client area includes the title bar, borders, and scroll bars.</span></span>  
  
 <span data-ttu-id="d60f6-106">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, aber Sie können sie aus der [Downloadcenter](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="d60f6-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-both-the-client-and-the-non-client-areas-of-a-form"></a><span data-ttu-id="d60f6-107">So drucken Sie sowohl den Client- als auch den Nicht-Clientbereich eines Formulars</span><span class="sxs-lookup"><span data-stu-id="d60f6-107">To print both the client and the non-client areas of a form</span></span>  
  
1.  <span data-ttu-id="d60f6-108">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="d60f6-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="d60f6-109">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d60f6-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="d60f6-110">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>fest.</span><span class="sxs-lookup"><span data-stu-id="d60f6-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="d60f6-111">Fügen Sie den folgenden Code in den passenden Ereignishandler ein (z. B. in den `Click` -Ereignishandler für eine Drucken- `Button`).</span><span class="sxs-lookup"><span data-stu-id="d60f6-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a Print `Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d60f6-112">Unter einigen Betriebssystemen werden von den <xref:System.Drawing.Graphics> -Methoden gezeichnete Text- oder Grafikelemente möglicherweise nicht ordnungsgemäß gedruckt.</span><span class="sxs-lookup"><span data-stu-id="d60f6-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="d60f6-113">Verwenden Sie in diesem Fall diese kompatible Druckmethode: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`</span><span class="sxs-lookup"><span data-stu-id="d60f6-113">In this case, use the compatible printing method: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60f6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d60f6-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="d60f6-115">PrintForm-Komponente</span><span class="sxs-lookup"><span data-stu-id="d60f6-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="d60f6-116">Gewusst wie: Drucken eines bildlauffähigen Formulars</span><span class="sxs-lookup"><span data-stu-id="d60f6-116">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
