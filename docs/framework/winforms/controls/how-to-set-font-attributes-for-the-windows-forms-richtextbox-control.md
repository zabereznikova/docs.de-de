---
title: "Gewusst wie: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms"
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
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fe122f509890715c398bef728a98ff874b61817
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Gewusst wie: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms
Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Optionen zum Formatieren des Texts angezeigt. Möglich markierten Zeichen fett, unterstrichen oder kursiv, mit der <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> Eigenschaft. Sie können mit dieser Eigenschaft außerdem die Größe und Schriftart der markierten Zeichen ändern. Die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Eigenschaft können Sie die Farbe der ausgewählten Zeichen zu ändern.  
  
### <a name="to-change-the-appearance-of-characters"></a>So ändern Sie die Darstellung von Zeichen  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> Eigenschaft, um eine passende Schriftart.  
  
     Um Benutzern das Festlegen der Schriftfamilie, die Größe und die Schriftart in einer Anwendung zu aktivieren, verwenden Sie in der Regel die <xref:System.Windows.Forms.FontDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die FontDialog-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Eigenschaft, um eine entsprechende Farbe.  
  
     Um Benutzern das Festlegen der Farbe in einer Anwendung zu aktivieren, verwenden Sie in der Regel die <xref:System.Windows.Forms.ColorDialog> Komponente. Eine Übersicht finden Sie unter [Übersicht über die ColorDialog-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
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
    >  Diese Eigenschaften wirken sich nur auf markierten Text aus bzw., wenn kein Text markiert ist, auf den Text, der an der aktuellen Position der Einfügemarke eingegeben wird. Informationen zum Auswählen von Text programmgesteuert finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
