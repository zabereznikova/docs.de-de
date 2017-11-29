---
title: 'Gewusst wie: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c942cb5f005177b74dd25a9725b4990553adbb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Gewusst wie: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit
Druckoptionen zur Entwurfszeit festgelegt werden kann, sollten Sie manchmal zur Laufzeit, wahrscheinlich aufgrund der vom Benutzer ausgewählten Optionen diese Optionen ändern. Sie können Erfassen von Benutzereingaben zum Drucken von einem Dokument mithilfe der <xref:System.Windows.Forms.PrintDialog> und die <xref:System.Drawing.Printing.PrintDocument> Komponenten.  
  
### <a name="to-change-print-options-programmatically"></a>So ändern Sie die Druckoptionen programmgesteuert  
  
1.  Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> und ein <xref:System.Drawing.Printing.PrintDocument> -Komponente in Ihr Formular.  
  
2.  Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft von der <xref:System.Windows.Forms.PrintDialog> auf der <xref:System.Drawing.Printing.PrintDocument> dem Formular hinzugefügt.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Anzeigen der <xref:System.Windows.Forms.PrintDialog> Komponente, indem die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Des Benutzers, die im Dialogfeld ausgewählten Druckoptionen kopiert werden die <xref:System.Drawing.Printing.PrinterSettings> Eigenschaft von der <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
