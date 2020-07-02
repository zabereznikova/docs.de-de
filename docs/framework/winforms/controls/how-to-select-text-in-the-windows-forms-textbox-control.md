---
title: Text im TextBox-Steuerelement auswählen
description: Erfahren Sie, wie Sie Textprogramm gesteuert im TextBox-Steuerelement Windows Forms auswählen. Erfahren Sie außerdem, wie Sie den Reader über die Position der gefundenen Zeichenfolge visuell benachrichtigen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: b8fdaff76461c4d6766dfc6afaef5e814d982834
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621560"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="0f03d-104">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f03d-104">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="0f03d-105">Sie können Textprogramm gesteuert im Windows Forms Steuerelement auswählen <xref:System.Windows.Forms.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="0f03d-105">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="0f03d-106">Wenn Sie z. b. eine Funktion erstellen, mit der Text nach einer bestimmten Zeichenfolge durchsucht wird, können Sie den Text auswählen, um den Reader visuell über die Position der gefundenen Zeichenfolge zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="0f03d-106">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="0f03d-107">So wählen Sie Textprogramm gesteuert aus</span><span class="sxs-lookup"><span data-stu-id="0f03d-107">To select text programmatically</span></span>  
  
1. <span data-ttu-id="0f03d-108">Legen Sie die- <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft auf den Anfang des Texts fest, den Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f03d-108">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="0f03d-109">Die- <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft ist eine Zahl, die die Einfügemarke in der Text Zeichenfolge angibt, wobei 0 die linke Position ist.</span><span class="sxs-lookup"><span data-stu-id="0f03d-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="0f03d-110">Wenn die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft auf einen Wert festgelegt ist, der gleich oder größer als die Anzahl der Zeichen im Textfeld ist, wird die Einfügemarke nach dem letzten Zeichen platziert.</span><span class="sxs-lookup"><span data-stu-id="0f03d-110">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="0f03d-111">Legen Sie die- <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft auf die Länge des Texts fest, den Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f03d-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="0f03d-112">Die- <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft ist ein numerischer Wert, der die Breite der Einfügemarke festlegt.</span><span class="sxs-lookup"><span data-stu-id="0f03d-112">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="0f03d-113">Wenn <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> auf eine Zahl größer als 0 festgelegt wird, wird die Anzahl der Zeichen beginnend mit der aktuellen Einfügemarke ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0f03d-113">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="0f03d-114">Optionale Greifen Sie über die-Eigenschaft auf den ausgewählten Text zu <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> .</span><span class="sxs-lookup"><span data-stu-id="0f03d-114">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="0f03d-115">Der folgende Code wählt den Inhalt eines Textfelds aus, wenn das-Ereignis des-Steuer Elements <xref:System.Windows.Forms.Control.Enter> auftritt.</span><span class="sxs-lookup"><span data-stu-id="0f03d-115">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="0f03d-116">In diesem Beispiel wird überprüft, ob das Textfeld einen Wert für die- <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft aufweist, die nicht `null` oder eine leere Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="0f03d-116">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="0f03d-117">Wenn das Textfeld den Fokus erhält, wird der aktuelle Text im Textfeld ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0f03d-117">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="0f03d-118">Der `TextBox1_Enter` Ereignishandler muss an das-Steuerelement gebunden werden. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0f03d-118">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="0f03d-119">Um dieses Beispiel zu testen, drücken Sie die Tab-Taste, bis das Textfeld den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="0f03d-119">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="0f03d-120">Wenn Sie in das Textfeld klicken, wird der Text nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0f03d-120">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0f03d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f03d-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="0f03d-122">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0f03d-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0f03d-123">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f03d-123">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="0f03d-124">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f03d-124">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0f03d-125">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="0f03d-125">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="0f03d-126">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="0f03d-126">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="0f03d-127">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f03d-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0f03d-128">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0f03d-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
