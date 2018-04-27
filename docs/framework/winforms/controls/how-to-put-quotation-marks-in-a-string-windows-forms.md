---
title: 'Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd7c6a460f24b1406ad914e20b9113920814737c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen (Windows Forms)
Möglicherweise benötigen Sie manchmal Anführungszeichen („ “) in einer Textzeichenfolge. Zum Beispiel:  
  
 She said, "You deserve a treat!" (Sie sagte: „Du verdienst eine Belohnung!“)  
  
 Als Alternative können Sie auch die <xref:Microsoft.VisualBasic.ControlChars.Quote> Feld als Konstante.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>So platzieren Sie Anführungszeichen in einer Zeichenfolge in Ihrem Code  
  
1.  Fügen Sie in Visual Basic zwei Anführungszeichen in einer Zeile als eine eingebettete Anführungszeichen ein. In Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], legen Sie die-Escapesequenz \\"als eingebetteten Anführungszeichen ein. Verwenden Sie z.B. folgenden Code, um die oben genannte Zeichenfolge zu erstellen.  
  
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
  
2.  Fügen Sie das ASCII- oder Unicode-Zeichen für ein Anführungszeichen ein. Verwenden Sie in Visual Basic das ASCII-Zeichen (34). Verwenden Sie in Visual c# das Unicode-Zeichen (\u0022).  
  
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
