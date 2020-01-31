---
title: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit aufzählen mit dem RichTextBox-Steuerelement
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
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743017"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms
Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement verfügt über zahlreiche Optionen, um den angezeigten Text zu formatieren. Sie können ausgewählte Absätze als aufzählt formatieren, indem Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>-Eigenschaft festlegen. Sie können auch die Eigenschaften <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>und <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> verwenden, um den Einzug von Absätzen in Bezug auf den linken und rechten Rand des Steuer Elements und den linken Rand anderer Textzeilen festzulegen.  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a>So formatieren Sie einen Absatz als Aufzählung  
  
1. Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> -Eigenschaft auf `true`fest.  
  
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
  
1. Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>-Eigenschaft auf eine ganze Zahl fest, die den Abstand zwischen dem linken Rand des Steuer Elements und dem linken Rand des Texts in Pixel darstellt.  
  
2. Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>-Eigenschaft auf eine ganze Zahl fest, die den Abstand zwischen dem linken Rand der ersten Textzeile im Absatz und dem linken Rand der nachfolgenden Zeilen desselben Absatzes in Pixel darstellt. Der Wert der <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>-Eigenschaft gilt nur für Zeilen in einem Absatz, die unter der ersten Zeile umschließt wurden.  
  
3. Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>-Eigenschaft auf eine ganze Zahl fest, die den Abstand zwischen dem rechten Rand des Steuer Elements und dem rechten Rand des Texts in Pixel darstellt.  
  
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
    > Alle genannten Eigenschaften wirken sich auf sämtliche Absätze, in denen Text markiert ist, sowie auf nach der aktuellen Einfügemarke eingegebenen Text aus. Wenn ein Benutzer beispielsweise ein Wort in einem Absatz markiert und dann den Einzug anpasst, wird die neue Einstellung auf den gesamten Absatz, in dem dieses Wort steht, und auf alle Absätze angewendet, die hinter diesem Absatz eingegeben werden. Informationen zum programmgesteuerten auswählen von Text finden Sie unter <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
