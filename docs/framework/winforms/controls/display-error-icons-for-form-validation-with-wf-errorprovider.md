---
title: 'Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: 237a61cc21a18805fa502c9870d8ea472ac54d71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms
Sie können eine Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente ein Fehlersymbol angezeigt wird, wenn der Benutzer ungültige Daten eingibt. Sie müssen mindestens zwei Steuerelemente im Formular aus, um zwischen ihnen Registerkarte und somit Aufrufen des Validierungscodes verfügen.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Um ein Fehlersymbol angezeigt wird, wenn der Wert eines Steuerelements ungültig ist  
  
1.  Hinzufügen von zwei Steuerelementen – z. B. Textfelder – zu einem Windows Form.  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.ErrorProvider> -Komponente zum Formular.  
  
3.  Wählen Sie das erste Steuerelement, und fügen Sie Code, dessen <xref:System.Windows.Forms.Control.Validating> -Ereignishandler. Damit kann für diesen Code ordnungsgemäß ausgeführt muss die Prozedur an das Ereignis bestehen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern an Zeit für Windows Forms führen](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Der folgende Code überprüft die Gültigkeit der Daten, die der Benutzer eingegeben hat. Wenn die Daten ungültig sind, werden die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> -Methode aufgerufen wird. Das erste Argument der <xref:System.Windows.Forms.ErrorProvider.SetError%2A> Methode gibt an, welches Steuerelement neben das Symbol angezeigt. Das zweite Argument ist der anzuzeigende Fehlertext.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Führen Sie das Projekt aus. Geben Sie in das erste Steuerelement, und klicken Sie dann Tab, um die zweite (in diesem Beispiel nicht numerisch) ungültige Daten. Wenn das Symbol "Fehler" angezeigt wird, stellen Sie den Mauszeiger an den Fehlertext finden Sie unter.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [Übersicht über die ErrorProvider-Komponente](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
