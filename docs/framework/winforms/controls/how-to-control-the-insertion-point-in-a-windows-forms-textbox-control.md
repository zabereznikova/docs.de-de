---
title: "Gewusst wie: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cc3dab3acafdb151cf14f81145ef47e5a6ff689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="9f4b0-102">Gewusst wie: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f4b0-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="9f4b0-103">Wenn ein Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement zunächst den Fokus erhält, ist das Standard-einfügen in das Textfeld auf der linken Seite des vorhandenen Text.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="9f4b0-104">Der Benutzer kann die Einfügemarke an der Stelle mit der Tastatur oder die Maus verschieben.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="9f4b0-105">Wenn das Textfeld verliert, und klicken Sie dann den Fokus erweitert, wird die Einfügemarke ablegen, wo der Benutzer zuletzt es platziert werden.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="9f4b0-106">In einigen Fällen kann dieses Verhalten für den Benutzer irritierend sein.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="9f4b0-107">In einem Textverarbeitungsprogramm, erwarten die Benutzer neue Zeichen nach einem vorhandenen Text angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="9f4b0-108">In einer Anwendung zur Dateneingabe erwarten die Benutzer neue Zeichen ersetzen alle vorhandenen Eintrag aus.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="9f4b0-109">Die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> und <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaften ermöglichen es Ihnen, die das Verhalten entsprechend Ihren Zweck zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="9f4b0-110">Steuern die Einfügemarke in einem Textfeldsteuerelement</span><span class="sxs-lookup"><span data-stu-id="9f4b0-110">To control the insertion point in a TextBox control</span></span>  
  
1.  <span data-ttu-id="9f4b0-111">Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="9f4b0-112">0 (null) wird die Einfügemarke direkt auf der linken Seite des ersten Zeichens platziert.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2.  <span data-ttu-id="9f4b0-113">(Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Eigenschaft, um die Länge des Texts, die Sie auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="9f4b0-114">Der folgende Code gibt die Einfügemarke immer auf 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="9f4b0-115">Die `TextBox1_Enter` Ereignishandler; Weitere Informationen an das Steuerelement gebunden werden muss, finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9f4b0-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="9f4b0-116">Sichtbarmachen der Einfügemarke an Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="9f4b0-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="9f4b0-117">Die <xref:System.Windows.Forms.TextBox> Einfügemarke befindet sich standardmäßig in ein neues Formular nur, wenn sichtbar der <xref:System.Windows.Forms.TextBox> Steuerelement steht an erster Stelle in der Aktivierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="9f4b0-118">Andernfalls die Einfügemarke angezeigt wird, nur dann, wenn Sie geben die <xref:System.Windows.Forms.TextBox> den Fokus der Tastatur oder die Maus.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="9f4b0-119">Um den Text im Feld der Einfügemarke auf eine neue Form standardmäßig sichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="9f4b0-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="9f4b0-120">Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft `0`.</span><span class="sxs-lookup"><span data-stu-id="9f4b0-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f4b0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f4b0-121">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="9f4b0-122">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f4b0-122">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="9f4b0-123">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f4b0-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="9f4b0-124">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="9f4b0-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="9f4b0-125">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9f4b0-125">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="9f4b0-126">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f4b0-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="9f4b0-127">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f4b0-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="9f4b0-128">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f4b0-128">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
