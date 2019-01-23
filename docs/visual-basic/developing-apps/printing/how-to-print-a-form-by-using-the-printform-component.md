---
title: 'Vorgehensweise: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 0a1a62627390c8839625862b9d43d61fc07ebf12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521568"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a><span data-ttu-id="e5b7f-102">Vorgehensweise: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5b7f-102">How to: Print a Form by Using the PrintForm Component (Visual Basic)</span></span>
<span data-ttu-id="e5b7f-103">Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie schnell ein Bild eines Formulars genau so drucken, wie es auf dem Bildschirm angezeigt wird, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="e5b7f-104">Die folgenden Vorgehensweisen zeigen das Ausgeben eines Formulars auf einem Drucker, in einem Druckvorschaufenster und in einer Encapsulated PostScript-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-104">The following procedures show how to print a form to a printer, to a print preview window, and to an Encapsulated PostScript file.</span></span>  
  
 <span data-ttu-id="e5b7f-105">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-a-form-to-the-default-printer"></a><span data-ttu-id="e5b7f-106">So drucken Sie ein Formular auf dem Standarddrucker</span><span class="sxs-lookup"><span data-stu-id="e5b7f-106">To print a form to the default printer</span></span>  
  
1.  <span data-ttu-id="e5b7f-107">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="e5b7f-108">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="e5b7f-109">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>fest.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="e5b7f-110">Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="e5b7f-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a><span data-ttu-id="e5b7f-111">So zeigen Sie ein Formular in einem Druckvorschaufenster an</span><span class="sxs-lookup"><span data-stu-id="e5b7f-111">To display a form in a print preview window</span></span>  
  
1.  <span data-ttu-id="e5b7f-112">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-112">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="e5b7f-113">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-113">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="e5b7f-114">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPreview>fest.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-114">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span></span>  
  
3.  <span data-ttu-id="e5b7f-115">Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="e5b7f-115">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a><span data-ttu-id="e5b7f-116">So drucken Sie ein Formular in eine Datei</span><span class="sxs-lookup"><span data-stu-id="e5b7f-116">To print a form to a file</span></span>  
  
1.  <span data-ttu-id="e5b7f-117">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-117">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="e5b7f-118">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-118">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="e5b7f-119">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToFile>fest.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-119">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span></span>  
  
3.  <span data-ttu-id="e5b7f-120">Wählen Sie optional die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> -Eigenschaft aus, und geben Sie den vollständigen Pfad und Dateinamen für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-120">Optionally, select the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> property and type the full path and file name for the destination file.</span></span>  
  
     <span data-ttu-id="e5b7f-121">Wenn Sie diesen Schritt überspringen, wird der Benutzer zur Laufzeit zur Eingabe eines Dateinamens aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e5b7f-121">If you skip this step, the user will be prompted for a file name at run time.</span></span>  
  
4.  <span data-ttu-id="e5b7f-122">Fügen Sie den folgenden Code in die entsprechenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="e5b7f-122">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e5b7f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5b7f-123">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>
- [<span data-ttu-id="e5b7f-124">Vorgehensweise: Drucken des Clientbereichs eines Formulars</span><span class="sxs-lookup"><span data-stu-id="e5b7f-124">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [<span data-ttu-id="e5b7f-125">Vorgehensweise: Drucken von Client- und Nicht-Client-Bereichen eines Formulars</span><span class="sxs-lookup"><span data-stu-id="e5b7f-125">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [<span data-ttu-id="e5b7f-126">Vorgehensweise: Drucken eines bildlauffähigen Formulars</span><span class="sxs-lookup"><span data-stu-id="e5b7f-126">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
- [<span data-ttu-id="e5b7f-127">PrintForm-Komponente</span><span class="sxs-lookup"><span data-stu-id="e5b7f-127">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
