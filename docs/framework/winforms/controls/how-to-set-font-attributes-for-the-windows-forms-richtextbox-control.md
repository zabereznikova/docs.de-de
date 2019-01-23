---
title: 'Vorgehensweise: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: 3793c33d378ee242656889434c7b29c415e9ec9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496204"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="8f21f-102">Vorgehensweise: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f21f-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="8f21f-103">Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Optionen zum Formatieren des Texts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f21f-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="8f21f-104">Möglich markierten Zeichen fett, unterstrichen oder kursiv formatiert ist, mit der <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f21f-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="8f21f-105">Sie können mit dieser Eigenschaft außerdem die Größe und Schriftart der markierten Zeichen ändern.</span><span class="sxs-lookup"><span data-stu-id="8f21f-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="8f21f-106">Die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Eigenschaft können Sie die Farbe der markierten Zeichen ändern.</span><span class="sxs-lookup"><span data-stu-id="8f21f-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="8f21f-107">So ändern Sie die Darstellung von Zeichen</span><span class="sxs-lookup"><span data-stu-id="8f21f-107">To change the appearance of characters</span></span>  
  
1.  <span data-ttu-id="8f21f-108">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> Eigenschaft eine geeignete Schriftart.</span><span class="sxs-lookup"><span data-stu-id="8f21f-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="8f21f-109">Um Benutzer zum Festlegen von Schriftfamilie, Größe und Schriftart in einer Anwendung zu aktivieren, verwenden Sie in der Regel die <xref:System.Windows.Forms.FontDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="8f21f-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="8f21f-110">Eine Übersicht finden Sie unter [Übersicht über die FontDialog-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8f21f-110">For an overview, see [FontDialog Component Overview](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="8f21f-111">Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Eigenschaft eine geeignete Farbe.</span><span class="sxs-lookup"><span data-stu-id="8f21f-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="8f21f-112">Um Benutzer zum Festlegen der Farbe in einer Anwendung zu aktivieren, verwenden Sie in der Regel die <xref:System.Windows.Forms.ColorDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="8f21f-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="8f21f-113">Eine Übersicht finden Sie unter [Übersicht über die ColorDialog-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8f21f-113">For an overview, see [ColorDialog Component Overview](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).</span></span>  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8f21f-114">Diese Eigenschaften wirken sich nur auf markierten Text aus bzw., wenn kein Text markiert ist, auf den Text, der an der aktuellen Position der Einfügemarke eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8f21f-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="8f21f-115">Informationen zum Markieren von Text programmgesteuert, finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f21f-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f21f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f21f-116">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="8f21f-117">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8f21f-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [<span data-ttu-id="8f21f-118">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="8f21f-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
