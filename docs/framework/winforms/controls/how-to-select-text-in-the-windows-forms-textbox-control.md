---
title: 'Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms'
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
ms.openlocfilehash: f96ac69f16eefb5bf4a0625ff83e207c289a105b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111435"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="0cd06-102">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd06-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="0cd06-103">Sie können Text programmgesteuert in das Windows Forms auswählen <xref:System.Windows.Forms.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0cd06-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="0cd06-104">Wenn Sie eine Funktion, die Text nach einer bestimmten Zeichenfolge sucht erstellen, können Sie beispielsweise den Text, den Reader, der die gefundene Zeichenfolge Position visuell Warnung auswählen.</span><span class="sxs-lookup"><span data-stu-id="0cd06-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="0cd06-105">Text programmgesteuert ausgewählt</span><span class="sxs-lookup"><span data-stu-id="0cd06-105">To select text programmatically</span></span>  
  
1.  <span data-ttu-id="0cd06-106">Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft an den Anfang des Texts, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="0cd06-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="0cd06-107">Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Eigenschaft ist eine Zahl, die die Einfügemarke innerhalb der Zeichenfolge des Texts angibt, wobei 0 die äußerste linke Position.</span><span class="sxs-lookup"><span data-stu-id="0cd06-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="0cd06-108">Wenn die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> -Eigenschaftensatz auf einen Wert gleich oder größer als die Anzahl der Zeichen in das Textfeld, das die Einfügemarke befindet sich hinter dem letzten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0cd06-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2.  <span data-ttu-id="0cd06-109">Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="0cd06-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="0cd06-110">Die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft ist ein numerischer Wert, der die Breite der Einfügemarke festlegt.</span><span class="sxs-lookup"><span data-stu-id="0cd06-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="0cd06-111">Festlegen der <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> auf eine Zahl größer als 0 bewirkt, diese Anzahl von Zeichen dass, die ausgewählt werden, beginnend mit der aktuellen Einfügemarke.</span><span class="sxs-lookup"><span data-stu-id="0cd06-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3.  <span data-ttu-id="0cd06-112">(Optional) Zugriff auf den markierten Text durch die <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0cd06-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="0cd06-113">Der Code unten wählt den Inhalt mit einem Feld beim des Steuerelements <xref:System.Windows.Forms.Control.Enter> Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="0cd06-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="0cd06-114">In diesem Beispiel wird überprüft, ob das Textfeld einen Wert für die <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft, die nicht `null` oder eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0cd06-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="0cd06-115">Wenn das Textfeld den Fokus erhält, ist der aktuelle Text in das Textfeld ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0cd06-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="0cd06-116">Die `TextBox1_Enter` Ereignishandler muss gebunden sein, auf das Steuerelement; Weitere Informationen, wie unter [Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0cd06-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="0cd06-117">Zum Testen dieses Beispiels, drücken Sie die Tab-Taste, bis das Textfeld den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="0cd06-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="0cd06-118">Wenn Sie in das Textfeld klicken, ist der Text nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0cd06-118">If you click in the text box, the text is unselected.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0cd06-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cd06-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="0cd06-120">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0cd06-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0cd06-121">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd06-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="0cd06-122">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd06-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0cd06-123">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="0cd06-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="0cd06-124">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="0cd06-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="0cd06-125">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd06-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="0cd06-126">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0cd06-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
