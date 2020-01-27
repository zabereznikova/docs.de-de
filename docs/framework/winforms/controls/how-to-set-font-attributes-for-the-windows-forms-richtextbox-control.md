---
title: Festlegen von Schriftart Attributen für das RichTextBox-Steuerelement
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
ms.openlocfilehash: f27256c155223df576ee3c42e6bf65270c870b0f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744852"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Gewusst wie: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms
Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement verfügt über zahlreiche Optionen, um den angezeigten Text zu formatieren. Sie können die ausgewählten Zeichen mit der <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>-Eigenschaft fett formatieren, unterstrichen machen oder kursiv formatieren. Sie können mit dieser Eigenschaft außerdem die Größe und Schriftart der markierten Zeichen ändern. Die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>-Eigenschaft ermöglicht es Ihnen, die Farbe der ausgewählten Zeichen zu ändern.  
  
### <a name="to-change-the-appearance-of-characters"></a>So ändern Sie die Darstellung von Zeichen  
  
1. Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>-Eigenschaft auf eine entsprechende Schriftart fest.  
  
     Um es Benutzern zu ermöglichen, die Schriftfamilie, die Größe und die Schriftart in einer Anwendung festzulegen, verwenden Sie in der Regel die <xref:System.Windows.Forms.FontDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die FontDialog-Komponente](fontdialog-component-overview-windows-forms.md).  
  
2. Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>-Eigenschaft auf eine entsprechende Farbe fest.  
  
     Um Benutzern das Festlegen der Farbe in einer Anwendung zu ermöglichen, verwenden Sie in der Regel die <xref:System.Windows.Forms.ColorDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die ColorDialog-Komponente](colordialog-component-overview-windows-forms.md).  
  
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
    > Diese Eigenschaften wirken sich nur auf markierten Text aus bzw., wenn kein Text markiert ist, auf den Text, der an der aktuellen Position der Einfügemarke eingegeben wird. Informationen zum programmgesteuerten auswählen von Text finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
