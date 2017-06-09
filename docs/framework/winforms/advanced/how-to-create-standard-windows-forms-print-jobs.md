---
title: "Gewusst wie: Erstellen von standardm&#228;&#223;igen Druckauftr&#228;gen in Windows Forms | Microsoft Docs"
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
  - "Drucken [Visual Basic], In Windows-Anwendungen"
  - "Drucken [Windows Forms]"
  - "Drucken [Windows Forms], Erstellen von Druckaufträgen"
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Erstellen von standardm&#228;&#223;igen Druckauftr&#228;gen in Windows Forms
Die Grundlage für das Drucken in Windows Forms bildet die <xref:System.Drawing.Printing.PrintDocument>\-Komponente, genauer gesagt das <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignis.  Indem Sie zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignisses Code schreiben, geben Sie an, was gedruckt werden soll und wie der Druck zu erfolgen hat.  
  
### So erstellen Sie einen Druckauftrag  
  
1.  Fügen Sie dem Formular eine <xref:System.Drawing.Printing.PrintDocument>\-Komponente hinzu.  
  
2.  Schreiben Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignisses.  
  
     Sie müssen Code für Ihre eigene Drucklogik erstellen.  Darüber hinaus müssen Sie das zu druckende Material angeben.  
  
     Im folgenden Codebeispiel wird im <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignishandler eine Beispielgrafik in Form eines roten Rechtecks erstellt, die als zu druckendes Material fungieren soll.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     Unter Umständen muss auch Code für das <xref:System.Drawing.Printing.PrintDocument.BeginPrint>\-Ereignis und das <xref:System.Drawing.Printing.PrintDocument.EndPrint>\-Ereignis geschrieben werden, wobei gegebenenfalls die Anzahl der noch zu druckenden Seiten durch eine ganze Zahl dargestellt wird, die bei jeder gedruckten Seite verringert wird.  
  
    > [!NOTE]
    >  Sie können dem Formular eine <xref:System.Windows.Forms.PrintDialog>\-Komponente hinzufügen, um Benutzern eine übersichtliche und effiziente Benutzeroberfläche \(UI\) zur Verfügung zu stellen.  Durch Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A>\-Eigenschaft der <xref:System.Windows.Forms.PrintDialog>\-Komponente können Sie Eigenschaften festlegen, die mit dem Druckdokument auf dem Formular verbunden sind.  Weitere Informationen über die <xref:System.Windows.Forms.PrintDialog>\-Komponente finden Sie unter [PrintDialog\-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Weitere Informationen zu den Besonderheiten von Druckaufträgen in Windows Forms, z. B. zur programmgesteuerten Erstellung eines Druckauftrags, finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## Siehe auch  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)