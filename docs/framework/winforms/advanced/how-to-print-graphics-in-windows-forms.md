---
title: "Gewusst wie: Drucken von Grafiken in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Grafiken, Drucken"
  - "Drucken [Windows Forms], Grafiken"
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Gewusst wie: Drucken von Grafiken in Windows Forms
In einer Windows\-basierten Anwendung müssen häufig Grafiken gedruckt werden.  Die <xref:System.Drawing.Graphics>\-Klasse stellt Methoden bereit, mit denen Objekte auf einem Gerät, z. B. auf einem Bildschirm oder Drucker, gezeichnet werden können.  
  
### So drucken Sie Grafiken  
  
1.  Fügen Sie dem Formular eine <xref:System.Drawing.Printing.PrintDocument>\-Komponente hinzu.  
  
2.  Um Informationen zur Art der zu druckenden Grafiken an den Drucker zu übergeben, verwenden Sie die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>\-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>\-Klasse im <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignishandler.  
  
     Im folgenden Codebeispiel wird ein Ereignishandler gezeigt, mit dem eine blaue Ellipse in einem Umgrenzungsrechteck erstellt wird.  Das Rechteck hat folgende Position und weist die folgenden Maße auf: beginnend bei 100, 150 mit einer Breite von 250 und einer Höhe von 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## Siehe auch  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Brush>   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)