---
title: 'Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530145"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="09105-102">Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="09105-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="09105-103">Sie können ein bearbeitbares Windows Forms-Text-Feld in ein schreibgeschütztes Steuerelement umwandeln.</span><span class="sxs-lookup"><span data-stu-id="09105-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="09105-104">Beispielsweise kann das Textfeld einen Wert angezeigt, der in der Regel bearbeitet wird, aber möglicherweise nicht aktuell aufgrund des Status der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="09105-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="09105-105">So erstellen ein nur-Lese Textfeld</span><span class="sxs-lookup"><span data-stu-id="09105-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="09105-106">Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="09105-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="09105-107">Mit der Eigenschaft auf festgelegt `true`, Benutzer können weiterhin einen Bildlauf durchführen und Hervorheben von Text in einem Textfeld ohne dass Änderungen.</span><span class="sxs-lookup"><span data-stu-id="09105-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="09105-108">Ein **Kopie** Befehl ist in einem Textfeld funktionsfähig, aber **Ausschneiden** und **einfügen** Befehle sind nicht.</span><span class="sxs-lookup"><span data-stu-id="09105-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09105-109">Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft wirkt sich nur auf ein Eingreifen des Benutzers zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="09105-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="09105-110">Sie können immer noch ändern Textfeldinhalt programmgesteuert zur Laufzeit durch Ändern der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="09105-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09105-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09105-111">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="09105-112">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="09105-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="09105-113">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09105-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="09105-114">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09105-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="09105-115">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="09105-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="09105-116">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09105-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="09105-117">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09105-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="09105-118">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="09105-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
