---
title: "Gewusst wie: Anzeigen einer Farbpalette mit der ColorDialog-Komponente | Microsoft Docs"
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
  - "Farbe (Dialogfeld), Anzeigen von Farbpaletten"
  - "Farbpaletten, Dialogfeld"
  - "Farbpaletten, Anzeigen in der ColorDialog-Komponente"
  - "Color-Eigenschaft"
  - "ColorDialog-Komponente, Anzeigen von Farbpaletten"
  - "Farben, Ermöglichen der Auswahl durch Benutzer"
  - "Farben, Anzeigen von Paletten"
  - "Paletten, Anzeigen von Farbpaletten"
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Anzeigen einer Farbpalette mit der ColorDialog-Komponente
Die [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)\-Komponente zeigt eine Farbpalette an und gibt eine Eigenschaft mit der vom Benutzer ausgewählten Farbe zurück.  
  
### So wählen Sie mit der ColorDialog\-Komponente eine Farbe aus  
  
1.  Zeigen Sie das Dialogfeld mithilfe der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode an.  
  
2.  Verwenden Sie die <xref:System.Windows.Forms.DialogResult>\-Eigenschaft, um zu bestimmen, wie das Dialogfeld geschlossen wurde.  
  
3.  Verwenden Sie die <xref:System.Windows.Forms.ColorDialog.Color%2A>\-Eigenschaft der <xref:System.Windows.Forms.ColorDialog>\-Komponente zum Festlegen der ausgewählten Farbe.  
  
     Im nachfolgenden Beispiel wird durch den <xref:System.Windows.Forms.Control.Click>\-Ereignishandler des <xref:System.Windows.Forms.Button>\-Steuerelements eine <xref:System.Windows.Forms.ColorDialog>\-Komponente geöffnet.  Wenn eine Farbe ausgewählt wurde und der Benutzer auf **OK** klickt, wird für die Hintergrundfarbe des <xref:System.Windows.Forms.Button>\-Steuerelements die ausgewählte Farbe festgelegt.  In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Button>\-Steuerelement und eine <xref:System.Windows.Forms.ColorDialog>\-Komponente verfügt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog\-Komponente](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)