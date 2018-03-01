---
title: "Übersicht über das TextBox-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d7312246c43157ca9cd6c7b41d2b110586721c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="e5cda-102">Übersicht über das TextBox-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e5cda-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e5cda-103">Windows Forms-Textfelder dienen, die vom Benutzer Eingabe abzurufen oder um Text anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5cda-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="e5cda-104">Die <xref:System.Windows.Forms.TextBox> Steuerelement wird im Allgemeinen für bearbeitbares Textfeld verwendet, obwohl sie auch schreibgeschützt festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5cda-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="e5cda-105">Textfelder können mehrere Zeilen angezeigt, Zeilenumbruch, um die Größe des Steuerelements und einfache Formatierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5cda-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="e5cda-106">Die <xref:System.Windows.Forms.TextBox> gesteuert Formatvorlage mit einem einzelnen Format für Text im Steuerelement angezeigt oder eingegeben.</span><span class="sxs-lookup"><span data-stu-id="e5cda-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="e5cda-107">Um mehrere Arten von formatiertem Text anzuzeigen, verwenden die <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e5cda-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="e5cda-108">Weitere Informationen finden Sie unter [Übersicht über das RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e5cda-108">For more information, see [RichTextBox Control Overview](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="e5cda-109">Arbeiten mit dem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e5cda-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="e5cda-110">Vom Steuerelement angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5cda-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="e5cda-111">Standardmäßig können Sie bis zu 2048 Zeichen in einem Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="e5cda-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="e5cda-112">Wenn Sie festlegen, die <xref:System.Windows.Forms.TextBox.Multiline%2A> Eigenschaft `true`, Sie können bis zu 32 KB Text eingeben.</span><span class="sxs-lookup"><span data-stu-id="e5cda-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="e5cda-113">Die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft kann zur Entwurfszeit im Fenster Eigenschaften zur Laufzeit im Code oder durch die Benutzereingabe zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e5cda-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="e5cda-114">Den aktuellen Inhalt eines Textfelds können zur Laufzeit abgerufen werden, durch Lesen der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5cda-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="e5cda-115">Das folgende Codebeispiel legt Text im Steuerelement zur Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="e5cda-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="e5cda-116">Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt; es muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5cda-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5cda-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5cda-117">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="e5cda-118">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5cda-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e5cda-119">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5cda-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e5cda-120">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="e5cda-120">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="e5cda-121">Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e5cda-121">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="e5cda-122">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5cda-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e5cda-123">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5cda-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e5cda-124">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e5cda-124">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
