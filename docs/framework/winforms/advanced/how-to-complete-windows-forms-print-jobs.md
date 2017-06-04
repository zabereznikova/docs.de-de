---
title: "Gewusst wie: Fertigstellen von Druckauftr&#228;gen in Windows Forms | Microsoft Docs"
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
  - "Druckaufträge, Abschließen in Windows Forms"
  - "Drucken [Windows Forms], Druckaufträge"
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Gewusst wie: Fertigstellen von Druckauftr&#228;gen in Windows Forms
In Textverarbeitungsprogrammen und anderen Anwendungen, in denen Druckaufträge bearbeitet werden, besteht häufig die Möglichkeit, eine Meldung anzuzeigen, die auf die Fertigstellung des Druckauftrags hinweist.  Sie können diese Funktionalität in Windows Forms bereitstellen, indem Sie das <xref:System.Drawing.Printing.PrintDocument.EndPrint>\-Ereignis der <xref:System.Drawing.Printing.PrintDocument>\-Komponente behandeln.  
  
 Für die folgende Prozedur ist es erforderlich, dass Sie eine Windows\-basierte Anwendung mit einer <xref:System.Drawing.Printing.PrintDocument>\-Komponente erstellt haben. Dies entspricht der üblichen Vorgehensweise, um das Drucken aus einer Windows\-basierten Anwendung zu aktivieren.  Weitere Informationen über das Drucken aus Windows Forms mit der <xref:System.Drawing.Printing.PrintDocument>\-Komponente finden Sie unter [Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### So führen Sie einen Druckauftrag aus  
  
1.  Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>\-Eigenschaft der <xref:System.Drawing.Printing.PrintDocument>\-Komponente fest.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Schreiben Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.EndPrint>\-Ereignisses.  
  
     Im folgenden Codebeispiel wird ein Meldungsfeld mit dem Hinweis angezeigt, dass der Druck des Dokuments abgeschlossen ist.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## Siehe auch  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)