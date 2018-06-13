---
title: 'Gewusst wie: Drucken eines bildlauffähigen Formulars (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: d43c2e0e564f6f0c37831cd3105a16c4bc4aaea0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584013"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a><span data-ttu-id="9cf6f-102">Gewusst wie: Drucken eines bildlauffähigen Formulars (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cf6f-102">How to: Print a Scrollable Form (Visual Basic)</span></span>
<span data-ttu-id="9cf6f-103">Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie schnell ein Bild eines Formulars drucken, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="9cf6f-104">Standardmäßig wird nur der aktuell sichtbare Teil des Formulars gedruckt; wenn ein Benutzer die Größe des Formulars zur Laufzeit geändert hat, wird das Bild möglicherweise nicht wie beabsichtigt gedruckt.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-104">By default, only the currently visible part of the form is printed; if a user has resized the form at run time, the image may not print as intended.</span></span> <span data-ttu-id="9cf6f-105">Die folgende Vorgehensweise veranschaulicht, wie der gesamte Clientbereich eines scrollbaren Formulars gedruckt wird, selbst wenn die Größe des Formulars geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-105">The following procedure shows how to print the complete client area of a scrollable form, even if the form has been resized.</span></span>  
  
 <span data-ttu-id="9cf6f-106">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a><span data-ttu-id="9cf6f-107">So drucken Sie den vollständigen Clientbereich eines scrollbaren Formulars</span><span class="sxs-lookup"><span data-stu-id="9cf6f-107">To print the complete client area of a scrollable form</span></span>  
  
1.  <span data-ttu-id="9cf6f-108">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="9cf6f-109">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component will be added to the component tray.</span></span>  
  
2.  <span data-ttu-id="9cf6f-110">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>fest.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="9cf6f-111">Fügen Sie den folgenden Code in den passenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="9cf6f-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9cf6f-112">Unter einigen Betriebssystemen werden von den <xref:System.Drawing.Graphics> -Methoden gezeichnete Text- oder Grafikelemente möglicherweise nicht ordnungsgemäß gedruckt.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="9cf6f-113">In diesem Fall kann der `Scrollable` -Parameter beim Drucken nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cf6f-113">In this case, you will not be able to print with the `Scrollable` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf6f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cf6f-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="9cf6f-115">PrintForm-Komponente</span><span class="sxs-lookup"><span data-stu-id="9cf6f-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="9cf6f-116">Gewusst wie: Drucken des Clientbereichs eines Formulars</span><span class="sxs-lookup"><span data-stu-id="9cf6f-116">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="9cf6f-117">Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars</span><span class="sxs-lookup"><span data-stu-id="9cf6f-117">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
