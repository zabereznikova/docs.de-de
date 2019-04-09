---
title: 'Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 1fa6e8a3642086f81d0a62502d801ec6ade9b3d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110715"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="a97b8-102">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a97b8-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="a97b8-103">Wenn ein Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement zunächst den Fokus erhält, wird das standardmäßige einfügen in das Textfeld auf der linken Seite des vorhandenen Text.</span><span class="sxs-lookup"><span data-stu-id="a97b8-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="a97b8-104">Der Benutzer kann die Einfügemarke die Tastatur oder Maus verschieben.</span><span class="sxs-lookup"><span data-stu-id="a97b8-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="a97b8-105">Wenn das Textfeld eingeschränkt, und klicken Sie dann wieder den Fokus erhält, wird die Einfügemarke ablegen, wo der Benutzer zuletzt es platziert werden.</span><span class="sxs-lookup"><span data-stu-id="a97b8-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="a97b8-106">In einigen Fällen kann dieses Verhalten für den Benutzer verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="a97b8-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="a97b8-107">In einem Textverarbeitungsprogramm, erwarten die Benutzer neue Zeichen nach der vorhandenen Text angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a97b8-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="a97b8-108">In eine Anwendung zur Dateneingabe erwarten die Benutzer neue Zeichen bestehende Einträge zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a97b8-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="a97b8-109">Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> und <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaften können Sie das Verhalten entsprechend Ihren Zweck zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a97b8-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="a97b8-110">Zum Steuern der Einfügemarke in einem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a97b8-110">To control the insertion point in a TextBox control</span></span>  
  
1.  <span data-ttu-id="a97b8-111">Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="a97b8-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="a97b8-112">0 (null) platziert die Einfügemarke direkt auf der linken Seite des ersten Zeichens.</span><span class="sxs-lookup"><span data-stu-id="a97b8-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2.  <span data-ttu-id="a97b8-113">(Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="a97b8-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="a97b8-114">Der folgende Code gibt die Einfügemarke immer 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="a97b8-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="a97b8-115">Die `TextBox1_Enter` Ereignishandler muss gebunden sein, auf das Steuerelement; Weitere Informationen, wie unter [Erstellen von Ereignishandlern in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a97b8-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="a97b8-116">Sichtbarmachen wird standardmäßig der Einfügemarke ein.</span><span class="sxs-lookup"><span data-stu-id="a97b8-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="a97b8-117">Die <xref:System.Windows.Forms.TextBox> Einfügemarke ist standardmäßig sichtbar in einer neuen Form nur, wenn die <xref:System.Windows.Forms.TextBox> Steuerelement wird in der Reihenfolge an erster Stelle.</span><span class="sxs-lookup"><span data-stu-id="a97b8-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="a97b8-118">Andernfalls die Einfügemarke angezeigt wird, nur, wenn Sie geben die <xref:System.Windows.Forms.TextBox> der Fokus mit der Tastatur oder Maus.</span><span class="sxs-lookup"><span data-stu-id="a97b8-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="a97b8-119">Um den Text die Einfügemarke auf eine neue Form standardmäßig sichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="a97b8-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="a97b8-120">Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft `0`.</span><span class="sxs-lookup"><span data-stu-id="a97b8-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97b8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a97b8-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a97b8-122">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a97b8-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a97b8-123">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a97b8-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a97b8-124">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="a97b8-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="a97b8-125">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a97b8-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a97b8-126">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a97b8-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a97b8-127">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a97b8-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a97b8-128">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a97b8-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
