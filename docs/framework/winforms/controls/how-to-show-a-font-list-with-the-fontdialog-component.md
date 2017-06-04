---
title: "Gewusst wie: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente | Microsoft Docs"
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
  - "Schriftart (Dialogfeld), Anzeigen"
  - "Font-Eigenschaft, Festlegen mit der FontDialog-Komponente"
  - "FontDialog-Komponente [Windows Forms]"
  - "Schriftarten, Attribute"
  - "Schriftarten, Auswählen"
  - "Schriftarten, Anzeigen einer Liste"
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente
Mit der [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)\-Komponente können Benutzer eine Schriftart auswählen und deren Anzeige ändern \(z. B. Schriftbreite und \-grad\).  
  
 Die im Dialogfeld ausgewählte Schriftart wird durch die <xref:System.Windows.Forms.FontDialog.Font%2A>\-Eigenschaft zurückgegeben.  Um die vom Benutzer ausgewählte Schriftart nutzen zu können, muss daher lediglich eine Eigenschaft gelesen werden.  
  
### So wählen Sie Schrifteigenschaften mit der FontDialog\-Komponente aus  
  
1.  Zeigen Sie das Dialogfeld mithilfe der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode an.  
  
2.  Verwenden Sie die <xref:System.Windows.Forms.DialogResult>\-Eigenschaft, um zu bestimmen, wie das Dialogfeld geschlossen wurde.  
  
3.  Legen Sie mit der <xref:System.Windows.Forms.FontDialog.Font%2A>\-Eigenschaft die gewünschte Schriftart fest.  
  
     Im nachfolgenden Beispiel wird durch den <xref:System.Windows.Forms.Control.Click>\-Ereignishandler des <xref:System.Windows.Forms.Button>\-Steuerelements eine <xref:System.Windows.Forms.FontDialog>\-Komponente geöffnet.  Wenn eine Schriftart ausgewählt wird und der Benutzer auf **OK** klickt, wird für die <xref:System.Windows.Forms.FontDialog.Font%2A>\-Eigenschaft eines <xref:System.Windows.Forms.TextBox>\-Steuerelements im Formular die ausgewählte Schriftart festgelegt.  In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Button>\-Steuerelement, ein <xref:System.Windows.Forms.TextBox>\-Steuerelement und eine <xref:System.Windows.Forms.FontDialog>\-Komponente verfügt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.FontDialog>   
 [FontDialog\-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)