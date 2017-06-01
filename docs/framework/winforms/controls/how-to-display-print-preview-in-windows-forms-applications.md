---
title: "Gewusst wie: Anzeigen der Seitenansicht in Windows Forms-Anwendungen | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Seitenansicht"
  - "Seitenansicht, Anzeigen"
  - "Drucken [Windows Forms], Seitenansicht"
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Anzeigen der Seitenansicht in Windows Forms-Anwendungen
Mit dem <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement können Sie es Benutzern ermöglichen, ein Dokument anzuzeigen, noch bevor es gedruckt wird.  
  
 Dazu müssen Sie eine Instanz der <xref:System.Drawing.Printing.PrintDocument>\-Klasse angeben. Dabei handelt es sich um das Dokument, das gedruckt werden soll.  Weitere Informationen über die Verwendung der Seitenansicht mit der <xref:System.Drawing.Printing.PrintDocument>\-Komponente finden Sie unter [Gewusst wie: Drucken in Windows Forms unter Verwendung der Seitenansicht](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Um ein <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement zur Laufzeit verwenden zu können, muss auf dem Computer des Benutzers ein Drucker lokal oder über ein Netzwerk installiert sein, da die <xref:System.Windows.Forms.PrintPreviewDialog>\-Komponente teilweise auf diese Art ermittelt, wie das Dokument beim Drucken aussieht.  
  
 Das <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement verwendet die <xref:System.Drawing.Printing.PrinterSettings>\-Klasse.  Zusätzlich verwendet das <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement die <xref:System.Drawing.Printing.PageSettings>\-Klasse, ebenso wie die <xref:System.Windows.Forms.PrintPreviewDialog>\-Komponente.  Das in der <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>\-Eigenschaft des <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelements angegebene Druckdokument verweist auf Instanzen der <xref:System.Drawing.Printing.PrinterSettings>\-Klasse und <xref:System.Drawing.Printing.PageSettings>\-Klasse, die zum Rendern des Dokuments im Vorschaufenster verwendet werden.  
  
### So zeigen Sie Seiten mit dem PrintPreviewDialog\-Steuerelement an  
  
-   Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode zum Anzeigen des Dialogfelds, und geben Sie dabei die zu verwendende <xref:System.Drawing.Printing.PrintDocument>\-Komponente an.  
  
     Im folgenden Codebeispiel wird vom <xref:System.Windows.Forms.Control.Click>\-Ereignishandler des <xref:System.Windows.Forms.Button>\-Steuerelements eine Instanz des <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelements geöffnet.  Das Druckdokument wird in der <xref:System.Windows.Forms.PrintDialog.Document%2A>\-Eigenschaft festgelegt.  Im nachstehenden Beispiel ist kein Druckdokument festgelegt.  
  
     In diesem Beispiel wird vorausgesetzt, dass das Formular über ein <xref:System.Windows.Forms.Button>\-Steuerelement, eine <xref:System.Drawing.Printing.PrintDocument>\-Komponente mit dem Namen`myDocument` und ein <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement verfügt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Siehe auch  
 [PrintDocument\-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)   
 [PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)