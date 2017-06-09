---
title: "Gewusst wie: Anzeigen von Fehlersymbolen f&#252;r die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Fehlersymbole"
  - "Fehlermeldungen, Anzeigen von Symbolen"
  - "ErrorProvider-Komponente [Windows Forms], Anzeigen von Fehlersymbolen"
  - "Fehler [Windows Forms], Anzeigen für Benutzer"
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Anzeigen von Fehlersymbolen f&#252;r die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms
Mit einer <xref:System.Windows.Forms.ErrorProvider>\-Komponente in Windows Forms können Sie ein Fehlersymbol anzeigen, wenn ein Benutzer ungültige Daten eingibt.  Das Formular muss mindestens zwei Steuerelemente enthalten, damit zwischen den Steuerelementen gewechselt und der Validierungscode dabei aufgerufen werden kann:  
  
### So zeigen Sie ein Fehlersymbol an, wenn der Wert eines Steuerelements ungültig ist  
  
1.  Fügen Sie zwei Steuerelemente, z. B. zwei Textfelder, zu Windows Forms hinzu.  
  
2.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.ErrorProvider>\-Komponente hinzu.  
  
3.  Wählen Sie das erste Steuerelement aus, und fügen Sie zu seinem <xref:System.Windows.Forms.Control.Validating>\-Ereignishandler Code hinzu.  Damit dieser Code ordnungsgemäß ausgeführt wird, muss die Prozedur mit dem Ereignis verbunden werden.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Der folgende Code überprüft die vom Benutzer eingegebenen Daten auf deren Gültigkeit. Falls die Daten ungültig sind, wird die <xref:System.Windows.Forms.ErrorProvider.SetError%2A>\-Methode aufgerufen.  Das erste Argument der <xref:System.Windows.Forms.ErrorProvider.SetError%2A>\-Methode gibt an, neben welchem Steuerelement das Symbol angezeigt wird.  Das zweite Argument gibt den angezeigten Fehlertext an.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Führen Sie das Projekt aus.  Geben Sie ungültige \(in diesem Fall nicht\-numerische\) Daten in das erste Steuerelement ein, und wechseln Sie anschließend zum zweiten Steuerelement.  Wenn das Fehlersymbol angezeigt wird, stellen Sie den Mauszeiger auf das Symbol, um den Fehlertext anzuzeigen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>   
 [Übersicht über die ErrorProvider\-Komponente](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)