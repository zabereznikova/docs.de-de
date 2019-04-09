---
title: 'Vorgehensweise: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms'
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
ms.openlocfilehash: 50a65a6828968f7bd9f1b17f5b8c8b1e4f70d051
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182909"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Vorgehensweise: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Optionen zum Formatieren des Texts angezeigt. Möglich markierten Zeichen fett, unterstrichen oder kursiv formatiert ist, mit der <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> Eigenschaft. Sie können mit dieser Eigenschaft außerdem die Größe und Schriftart der markierten Zeichen ändern. Die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Eigenschaft können Sie die Farbe der markierten Zeichen ändern.  
  
### <a name="to-change-the-appearance-of-characters"></a>So ändern Sie die Darstellung von Zeichen  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> Eigenschaft eine geeignete Schriftart.  
  
     Um Benutzer zum Festlegen von Schriftfamilie, Größe und Schriftart in einer Anwendung zu aktivieren, verwenden Sie in der Regel die <xref:System.Windows.Forms.FontDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die FontDialog-Komponente](fontdialog-component-overview-windows-forms.md).  
  
2.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Eigenschaft eine geeignete Farbe.  
  
     Um Benutzer zum Festlegen der Farbe in einer Anwendung zu aktivieren, verwenden Sie in der Regel die <xref:System.Windows.Forms.ColorDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die ColorDialog-Komponente](colordialog-component-overview-windows-forms.md).  
  
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
    >  Diese Eigenschaften wirken sich nur auf markierten Text aus bzw., wenn kein Text markiert ist, auf den Text, der an der aktuellen Position der Einfügemarke eingegeben wird. Informationen zum Markieren von Text programmgesteuert, finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
