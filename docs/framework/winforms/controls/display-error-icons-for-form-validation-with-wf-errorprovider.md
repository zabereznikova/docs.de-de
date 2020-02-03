---
title: Anzeigen von Fehler Symbolen für die Formular Validierung mit der ErrorProvider-Komponente
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
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745909"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms
Sie können eine Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente verwenden, um ein Fehler Symbol anzuzeigen, wenn der Benutzer ungültige Daten eingibt. Sie müssen über mindestens zwei Steuerelemente auf dem Formular verfügen, um zwischen Ihnen zu Tabstopps und somit den Validierungscode aufrufen zu können.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>So zeigen Sie ein Fehler Symbol an, wenn der Wert eines Steuer Elements ungültig ist  
  
1. Fügen Sie zwei Steuerelemente – z. b. Textfelder – zu einem Windows Form hinzu.  
  
2. Fügen Sie dem Formular eine <xref:System.Windows.Forms.ErrorProvider> Komponente hinzu.  
  
3. Wählen Sie das erste Steuerelement aus, und fügen Sie seinem <xref:System.Windows.Forms.Control.Validating>-Ereignishandler Code hinzu. Damit dieser Code ordnungsgemäß ausgeführt werden kann, muss die Prozedur mit dem Ereignis verbunden werden. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Der folgende Code testet die Gültigkeit der Daten, die der Benutzer eingegeben hat. Wenn die Daten ungültig sind, wird die <xref:System.Windows.Forms.ErrorProvider.SetError%2A>-Methode aufgerufen. Das erste Argument der <xref:System.Windows.Forms.ErrorProvider.SetError%2A>-Methode gibt an, welches Steuerelement neben dem-Symbol angezeigt werden soll. Das zweite Argument ist der anzuzeigende Fehlertext.  
  
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
  
     (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Führen Sie das Projekt aus. Geben Sie ungültige (in diesem Beispiel nicht numerische) Daten in das erste Steuerelement ein, und drücken Sie dann die Tab-Taste. Wenn das Fehler Symbol angezeigt wird, zeigen Sie mit dem Mauszeiger darauf, um den Fehlertext anzuzeigen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Übersicht über die ErrorProvider-Komponente](errorprovider-component-overview-windows-forms.md)
- [Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
