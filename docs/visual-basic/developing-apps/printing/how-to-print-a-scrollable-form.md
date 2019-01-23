---
title: 'Vorgehensweise: Drucken eines bildlauffähigen Formulars (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: 6cec75eae8046befeb37da39e0b788f045ff4149
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552501"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a><span data-ttu-id="e91a6-102">Vorgehensweise: Drucken eines bildlauffähigen Formulars (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e91a6-102">How to: Print a Scrollable Form (Visual Basic)</span></span>
<span data-ttu-id="e91a6-103">Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie schnell ein Bild eines Formulars drucken, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e91a6-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="e91a6-104">Standardmäßig wird nur der aktuell sichtbare Teil des Formulars gedruckt; wenn ein Benutzer die Größe des Formulars zur Laufzeit geändert hat, wird das Bild möglicherweise nicht wie beabsichtigt gedruckt.</span><span class="sxs-lookup"><span data-stu-id="e91a6-104">By default, only the currently visible part of the form is printed; if a user has resized the form at run time, the image may not print as intended.</span></span> <span data-ttu-id="e91a6-105">Die folgende Vorgehensweise veranschaulicht, wie der gesamte Clientbereich eines scrollbaren Formulars gedruckt wird, selbst wenn die Größe des Formulars geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="e91a6-105">The following procedure shows how to print the complete client area of a scrollable form, even if the form has been resized.</span></span>  
  
 <span data-ttu-id="e91a6-106">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e91a6-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a><span data-ttu-id="e91a6-107">So drucken Sie den vollständigen Clientbereich eines scrollbaren Formulars</span><span class="sxs-lookup"><span data-stu-id="e91a6-107">To print the complete client area of a scrollable form</span></span>  
  
1.  <span data-ttu-id="e91a6-108">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e91a6-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="e91a6-109">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e91a6-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component will be added to the component tray.</span></span>  
  
2.  <span data-ttu-id="e91a6-110">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>fest.</span><span class="sxs-lookup"><span data-stu-id="e91a6-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="e91a6-111">Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="e91a6-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e91a6-112">Unter einigen Betriebssystemen werden von den <xref:System.Drawing.Graphics> -Methoden gezeichnete Text- oder Grafikelemente möglicherweise nicht ordnungsgemäß gedruckt.</span><span class="sxs-lookup"><span data-stu-id="e91a6-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="e91a6-113">In diesem Fall kann der `Scrollable` -Parameter beim Drucken nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e91a6-113">In this case, you will not be able to print with the `Scrollable` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91a6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e91a6-114">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>
- [<span data-ttu-id="e91a6-115">PrintForm-Komponente</span><span class="sxs-lookup"><span data-stu-id="e91a6-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
- [<span data-ttu-id="e91a6-116">Vorgehensweise: Drucken des Clientbereichs eines Formulars</span><span class="sxs-lookup"><span data-stu-id="e91a6-116">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [<span data-ttu-id="e91a6-117">Vorgehensweise: Drucken von Client- und Nicht-Client-Bereichen eines Formulars</span><span class="sxs-lookup"><span data-stu-id="e91a6-117">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
