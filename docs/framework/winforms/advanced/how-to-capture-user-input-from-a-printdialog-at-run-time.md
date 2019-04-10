---
title: 'Vorgehensweise: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit'
ms.date: 03/30/2017
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
ms.openlocfilehash: 2aaf988f362baf9cd80eb16e4a08f7f65a5077bb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311421"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Vorgehensweise: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit
Während Sie die Optionen in Bezug auf Drucken zur Entwurfszeit festlegen können, möchten Sie auch diese Optionen zur Laufzeit, wahrscheinlich aufgrund einer vom Benutzer vorgenommene Auswahl zu ändern. Sie können Erfassen von Benutzereingaben zum Drucken von einem Dokument mithilfe der <xref:System.Windows.Forms.PrintDialog> und <xref:System.Drawing.Printing.PrintDocument> Komponenten.  
  
### <a name="to-change-print-options-programmatically"></a>So ändern Sie die Druckoptionen programmgesteuert  
  
1. Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> und <xref:System.Drawing.Printing.PrintDocument> Ihrem Formular.  
  
2. Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft der <xref:System.Windows.Forms.PrintDialog> auf die <xref:System.Drawing.Printing.PrintDocument> zum Formular hinzugefügt.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. Anzeigen der <xref:System.Windows.Forms.PrintDialog> -Komponente mithilfe der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. Der Benutzer, die aus dem Dialogfeld ausgewählten Druckoptionen kopiert werden die <xref:System.Drawing.Printing.PrinterSettings> Eigenschaft der <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
