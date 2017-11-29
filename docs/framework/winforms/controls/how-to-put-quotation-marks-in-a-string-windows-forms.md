---
title: "Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)"
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
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a4141a27a3b195dbb747a827d2bd9426a948f83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)
Möglicherweise benötigen Sie manchmal Anführungszeichen („ “) in einer Textzeichenfolge. Zum Beispiel:  
  
 She said, "You deserve a treat!" (Sie sagte: „Du verdienst eine Belohnung!“)  
  
 Als Alternative können Sie auch die <xref:Microsoft.VisualBasic.ControlChars.Quote> Feld als Konstante.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>So platzieren Sie Anführungszeichen in einer Zeichenfolge in Ihrem Code  
  
1.  In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] fügen Sie zwei Anführungszeichen in einer Zeile als eingebettetes Anführungszeichen ein. In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] fügen Sie die Escapesequenz \\" als eingebettetes Anführungszeichen ein. Verwenden Sie z.B. folgenden Code, um die oben genannte Zeichenfolge zu erstellen.  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     - oder -   
  
2.  Fügen Sie das ASCII- oder Unicode-Zeichen für ein Anführungszeichen ein. Verwenden Sie in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] das ASCII-Zeichen (34). Verwenden Sie in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] das Unicode-Zeichen (\u0022).  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  In diesem Beispiel können Sie \u0022 nicht verwenden, da Sie keinen universellen Zeichennamen verwenden dürfen, der ein Zeichen im Basiszeichensatz bezeichnet. Andernfalls wird C3851 ausgelöst. Weitere Informationen finden Sie unter [Compilerfehler C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).  
  
     - oder -   
  
3.  Sie können auch eine Konstante für das Zeichen definieren und bei Bedarf verwenden.  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextBox>  
 <xref:Microsoft.VisualBasic.ControlChars.Quote>  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
