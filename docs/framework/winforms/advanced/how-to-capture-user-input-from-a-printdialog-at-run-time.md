---
title: "Gewusst wie: Erfassen von Benutzereingaben in einem &quot;PrintDialog&quot; zur Laufzeit | Microsoft Docs"
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
  - "Druckoptionen"
  - "Druckoptionen, Ändern zur Laufzeit"
  - "Drucken [Windows Forms], Optionen"
  - "Laufzeit, Ändern von Druckoptionen"
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Erfassen von Benutzereingaben in einem &quot;PrintDialog&quot; zur Laufzeit
Zwar können die Druckoptionen zur Entwurfszeit festgelegt werden, gelegentlich müssen diese jedoch zur Laufzeit geändert werden, in der Regel aufgrund der vom Benutzer getroffenen Auswahl.  Benutzereingaben zum Drucken von Dokumenten können mit der <xref:System.Windows.Forms.PrintDialog>\-Komponente und der <xref:System.Drawing.Printing.PrintDocument>\-Komponente erfasst werden.  
  
### So ändern Sie Druckoptionen programmgesteuert  
  
1.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.PrintDialog>\-Komponente und eine <xref:System.Drawing.Printing.PrintDocument>\-Komponente hinzu.  
  
2.  Legen Sie die <xref:System.Windows.Forms.PrintDialog.Document%2A>\-Eigenschaft von <xref:System.Windows.Forms.PrintDialog> auf die dem Formular hinzugefügte <xref:System.Drawing.Printing.PrintDocument>\-Komponente fest.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Zeigen Sie die <xref:System.Windows.Forms.PrintDialog>\-Komponente an, indem Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode verwenden.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Die vom Benutzer im Dialogfeld ausgewählten Druckoptionen werden in die <xref:System.Drawing.Printing.PrinterSettings>\-Eigenschaft der <xref:System.Drawing.Printing.PrintDocument>\-Komponente kopiert.  
  
## Siehe auch  
 [Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)