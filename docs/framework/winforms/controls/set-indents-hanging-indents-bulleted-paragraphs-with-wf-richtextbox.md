---
title: 'Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 95ba276f3b2682d5b5bcaaa49916e856eb580632
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537686"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms
Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Optionen zum Formatieren des Texts angezeigt. Sie können ausgewählte Absätze als Aufzählung formatieren, durch Festlegen der <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> Eigenschaft. Sie können auch die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, und <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Eigenschaften den Einzug der Absätze relativ zum linken und rechten Rands des Steuerelements und dem linken Rand anderer Textzeilen festlegen.  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a>So formatieren Sie einen Absatz als Aufzählung  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>-Eigenschaft auf `true` fest.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a>So ziehen Sie einen Absatz ein  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> Eigenschaft, um eine ganze Zahl, die den Abstand zwischen dem linken Rand des Steuerelements und dem linken Rand des Texts in Pixel darstellt.  
  
2.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Eigenschaft, um eine ganze Zahl, die den Abstand zwischen dem linken Rand der ersten Zeile des Texts im Absatz und dem linken Rand der folgenden Zeilen in der gleichen Absatz in Pixel darstellt. Der Wert, der die <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> Eigenschaft gilt nur für Zeilen in einem Absatz, die unterhalb der ersten Zeile umbrochen wurden.  
  
3.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> Eigenschaft, um eine ganze Zahl, die den Abstand zwischen dem rechten Rand des Steuerelements und dem rechten Rand des Texts in Pixel darstellt.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  Alle genannten Eigenschaften wirken sich auf sämtliche Absätze, in denen Text markiert ist, sowie auf nach der aktuellen Einfügemarke eingegebenen Text aus. Wenn ein Benutzer beispielsweise ein Wort in einem Absatz markiert und dann den Einzug anpasst, wird die neue Einstellung auf den gesamten Absatz, in dem dieses Wort steht, und auf alle Absätze angewendet, die hinter diesem Absatz eingegeben werden. Informationen über das Auswählen von Text programmgesteuert finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
