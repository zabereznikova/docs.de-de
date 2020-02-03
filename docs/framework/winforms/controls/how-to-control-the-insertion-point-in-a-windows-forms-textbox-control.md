---
title: Steuern der Einfügemarke im TextBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742201"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="dff97-102">Gewusst wie: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dff97-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="dff97-103">Wenn ein Windows Forms <xref:System.Windows.Forms.TextBox>-Steuerelement den Fokus erhält, wird die Standard Einfügung innerhalb des Textfelds auf der linken Seite von vorhandenem Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dff97-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="dff97-104">Der Benutzer kann die Einfügemarke mit der Tastatur oder der Maus verschieben.</span><span class="sxs-lookup"><span data-stu-id="dff97-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="dff97-105">Wenn das Textfeld den Fokus verliert und dann wieder erhält, ist die Einfügemarke an der Stelle, an der der Benutzer Sie zuletzt platziert hat.</span><span class="sxs-lookup"><span data-stu-id="dff97-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="dff97-106">In einigen Fällen kann dieses Verhalten dem Benutzer zu einem verwirrend werden.</span><span class="sxs-lookup"><span data-stu-id="dff97-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="dff97-107">In einer Textverarbeitungsanwendung erwartet der Benutzer möglicherweise, dass neue Zeichen nach vorhandenem Text angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dff97-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="dff97-108">In einer Dateneingabe Anwendung erwartet der Benutzer möglicherweise, dass neue Zeichen einen vorhandenen Eintrag ersetzen.</span><span class="sxs-lookup"><span data-stu-id="dff97-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="dff97-109">Mit den Eigenschaften <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> und <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> können Sie das Verhalten an ihren Zweck anpassen.</span><span class="sxs-lookup"><span data-stu-id="dff97-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="dff97-110">So steuern Sie die Einfügemarke in einem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dff97-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="dff97-111">Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="dff97-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="dff97-112">NULL platziert die Einfügemarke direkt links vom ersten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="dff97-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="dff97-113">Optionale Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>-Eigenschaft auf die Länge des Texts fest, den Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="dff97-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="dff97-114">Der folgende Code gibt immer die Einfügemarke auf 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="dff97-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="dff97-115">Der `TextBox1_Enter` Ereignishandler muss an das-Steuerelement gebunden werden. Weitere Informationen finden Sie unter [Erstellen von Ereignis Handlern in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="dff97-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="dff97-116">Standardmäßiges sichtbar machen der Einfügemarke</span><span class="sxs-lookup"><span data-stu-id="dff97-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="dff97-117">Die <xref:System.Windows.Forms.TextBox> Einfügemarke ist standardmäßig nur in einem neuen Format sichtbar, wenn das <xref:System.Windows.Forms.TextBox> Steuerelement in der Aktivier Reihenfolge an erster Stelle steht.</span><span class="sxs-lookup"><span data-stu-id="dff97-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="dff97-118">Andernfalls wird die Einfügemarke nur angezeigt, wenn Sie die <xref:System.Windows.Forms.TextBox> den Fokus mit der Tastatur oder der Maus versehen.</span><span class="sxs-lookup"><span data-stu-id="dff97-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="dff97-119">So machen Sie die Textfeld-Einfügemarke standardmäßig in einem neuen Formular sichtbar</span><span class="sxs-lookup"><span data-stu-id="dff97-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="dff97-120">Legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A>-Eigenschaft des <xref:System.Windows.Forms.TextBox>-Steuer Elements auf `0`fest.</span><span class="sxs-lookup"><span data-stu-id="dff97-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff97-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dff97-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="dff97-122">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dff97-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="dff97-123">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dff97-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="dff97-124">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="dff97-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="dff97-125">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="dff97-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="dff97-126">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dff97-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="dff97-127">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dff97-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="dff97-128">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dff97-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
