---
title: Übersicht über das TextBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 716195238e99938c8c416466fc84c2eff0bc7ba9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709786"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="8a347-102">Übersicht über das TextBox-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8a347-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="8a347-103">Windows Forms-Textfelder werden Eingaben von den Benutzer erhalten oder zum Anzeigen von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a347-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="8a347-104">Die <xref:System.Windows.Forms.TextBox> Steuerelement wird im Allgemeinen für bearbeitbaren Text verwendet, obwohl sie auch schreibgeschützt festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8a347-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="8a347-105">Textfelder können mehrere Zeilen angezeigt, Umbrechen von Text auf die Größe des Steuerelements und fügen die einfache Formatierung.</span><span class="sxs-lookup"><span data-stu-id="8a347-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="8a347-106">Die <xref:System.Windows.Forms.TextBox> -Steuerelement stellt einen einzelnen Formatstil für Text angezeigt oder in das Steuerelement eingegeben.</span><span class="sxs-lookup"><span data-stu-id="8a347-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="8a347-107">Um mehrere Arten von formatiertem Text anzuzeigen, verwenden die <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8a347-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="8a347-108">Weitere Informationen finden Sie unter [Übersicht über das RichTextBox-Steuerelement](richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8a347-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="8a347-109">Arbeiten mit dem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8a347-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="8a347-110">Vom Steuerelement angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8a347-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8a347-111">Standardmäßig können Sie bis zu 2048 Zeichen in einem Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="8a347-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="8a347-112">Setzen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> Eigenschaft `true`, können Sie bis zu 32 KB Text eingeben.</span><span class="sxs-lookup"><span data-stu-id="8a347-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="8a347-113">Die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft kann zur Entwurfszeit im Fenster Eigenschaften zur Laufzeit im Code oder durch die Benutzereingabe zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8a347-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="8a347-114">Den aktuellen Inhalt eines Textfelds können zur Laufzeit abgerufen werden, durch Lesen der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8a347-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="8a347-115">Das folgende Codebeispiel legt Text im Steuerelement zur Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="8a347-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="8a347-116">Die `InitializeMyControl` -Prozedur wird nicht automatisch ausgeführt; muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8a347-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a347-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a347-117">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="8a347-118">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a347-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="8a347-119">Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a347-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="8a347-120">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="8a347-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="8a347-121">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8a347-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="8a347-122">Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a347-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="8a347-123">Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an</span><span class="sxs-lookup"><span data-stu-id="8a347-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="8a347-124">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8a347-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
