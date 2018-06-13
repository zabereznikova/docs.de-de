---
title: 'Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: 41bfb2bc1a1ead5bb289264c44145b88721efe49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534299"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Gewusst wie: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms
Ein Kennwortfeld ist ein Windows Forms-Textfeld, in dem Platzhalterzeichen angezeigt, während ein Benutzer, eine Zeichenfolge eingibt.  
  
### <a name="to-create-a-password-text-box"></a>So erstellen das Textfeld "Kennwort"  
  
1.  Festlegen der <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft von der <xref:System.Windows.Forms.TextBox> Steuerelement auf ein bestimmtes Zeichen.  
  
     Die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft gibt das Zeichen im Textfeld angezeigt. Geben Sie z. B. wenn Sternchen im Kennwortfeld angezeigt werden sollen, * für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft im Eigenschaftenfenster angezeigt. Unabhängig davon, welche Zeichen, die ein Benutzer in das Textfeld eingibt, wird anschließend ein Sternchen angezeigt.  
  
2.  (Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Eigenschaft. Die Eigenschaft bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können. Wenn die maximale Länge überschritten wird, das System gibt einen Signalton aus, und das Textfeld akzeptiert keine weiteren Zeichen. Beachten Sie, dass Sie nicht dazu, wie die maximale Länge von Kennwörtern mithilfe Hacker, die versuchen werden kann, das Kennwort erraten möchten.  
  
     Im folgenden Codebeispiel wird gezeigt, wie ein Textfeld, das initialisiert werden, die akzeptiert einer Zeichenfolge bis zu 14 Zeichen lang sein und Sternchen anstelle der Zeichenfolge angezeigt wird. Die `InitializeMyControl` Prozedur wird nicht automatisch ausgeführt; es muss aufgerufen werden.  
  
    > [!IMPORTANT]
    >  Mithilfe der <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft in einem Textfeld können Sie sicherstellen, dass andere Personen das Kennwort eines Benutzers zu bestimmen, ob sie die Beobachtung. Durch diese Sicherheitsmaßnahme deckt keine Art von Speicher oder die Übertragung des Kennworts, die aufgrund Ihrer Anwendungslogik auftreten können. Da der eingegebene Text nicht in keiner Weise verschlüsselt ist, sollten Sie sie behandeln, wie alle anderen vertraulichen Daten. Obwohl es nicht als solche angezeigt wird, wird das Kennwort (es sei denn, Sie einige zusätzliche Sicherheitsmaßnahme implementiert haben) immer noch als nur-Text-Zeichenfolge behandelt.  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextBox>  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
