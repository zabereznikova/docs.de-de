---
title: 'Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 5f8e620fce2b85d3f3cdb66bf80967f8eb281361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590012"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a><span data-ttu-id="11440-102">Gewusst wie: Drucken eines Formulars mithilfe der PrintForm-Komponente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11440-102">How to: Print a Form by Using the PrintForm Component (Visual Basic)</span></span>
<span data-ttu-id="11440-103">Mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente können Sie schnell ein Bild eines Formulars genau so drucken, wie es auf dem Bildschirm angezeigt wird, ohne eine <xref:System.Drawing.Printing.PrintDocument> -Komponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="11440-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="11440-104">Die folgenden Vorgehensweisen zeigen das Ausgeben eines Formulars auf einem Drucker, in einem Druckvorschaufenster und in einer Encapsulated PostScript-Datei.</span><span class="sxs-lookup"><span data-stu-id="11440-104">The following procedures show how to print a form to a printer, to a print preview window, and to an Encapsulated PostScript file.</span></span>  
  
 <span data-ttu-id="11440-105">Die PowerPack-Steuerelemente sind nicht mehr in Visual Studio enthalten, Sie können sie jedoch aus dem [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="11440-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-a-form-to-the-default-printer"></a><span data-ttu-id="11440-106">So drucken Sie ein Formular auf dem Standarddrucker</span><span class="sxs-lookup"><span data-stu-id="11440-106">To print a form to the default printer</span></span>  
  
1.  <span data-ttu-id="11440-107">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="11440-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="11440-108">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="11440-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="11440-109">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>fest.</span><span class="sxs-lookup"><span data-stu-id="11440-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="11440-110">Fügen Sie den folgenden Code in den passenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="11440-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a><span data-ttu-id="11440-111">So zeigen Sie ein Formular in einem Druckvorschaufenster an</span><span class="sxs-lookup"><span data-stu-id="11440-111">To display a form in a print preview window</span></span>  
  
1.  <span data-ttu-id="11440-112">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="11440-112">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="11440-113">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="11440-113">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="11440-114">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToPreview>fest.</span><span class="sxs-lookup"><span data-stu-id="11440-114">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span></span>  
  
3.  <span data-ttu-id="11440-115">Fügen Sie den folgenden Code in den passenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="11440-115">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a><span data-ttu-id="11440-116">So drucken Sie ein Formular in eine Datei</span><span class="sxs-lookup"><span data-stu-id="11440-116">To print a form to a file</span></span>  
  
1.  <span data-ttu-id="11440-117">Klicken Sie in der **Toolbox**auf die Registerkarte **Visual Basic PowerPacks** , und ziehen Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="11440-117">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="11440-118">Die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> -Komponente wird der Komponentenleiste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="11440-118">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="11440-119">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> auf <xref:System.Drawing.Printing.PrintAction.PrintToFile>fest.</span><span class="sxs-lookup"><span data-stu-id="11440-119">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span></span>  
  
3.  <span data-ttu-id="11440-120">Wählen Sie optional die <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> -Eigenschaft aus, und geben Sie den vollständigen Pfad und Dateinamen für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="11440-120">Optionally, select the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> property and type the full path and file name for the destination file.</span></span>  
  
     <span data-ttu-id="11440-121">Wenn Sie diesen Schritt überspringen, wird der Benutzer zur Laufzeit zur Eingabe eines Dateinamens aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="11440-121">If you skip this step, the user will be prompted for a file name at run time.</span></span>  
  
4.  <span data-ttu-id="11440-122">Fügen Sie den folgenden Code in den passenden Ereignishandler (z. B. in der `Click` -Ereignishandler für ein **Drucken**`Button`).</span><span class="sxs-lookup"><span data-stu-id="11440-122">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11440-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11440-123">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>  
 [<span data-ttu-id="11440-124">Gewusst wie: Drucken des Clientbereichs eines Formulars</span><span class="sxs-lookup"><span data-stu-id="11440-124">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="11440-125">Gewusst wie: Drucken von Client- und Nicht-Client-Bereichen eines Formulars</span><span class="sxs-lookup"><span data-stu-id="11440-125">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [<span data-ttu-id="11440-126">Gewusst wie: Drucken eines bildlauffähigen Formulars</span><span class="sxs-lookup"><span data-stu-id="11440-126">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)  
 [<span data-ttu-id="11440-127">PrintForm-Komponente</span><span class="sxs-lookup"><span data-stu-id="11440-127">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
