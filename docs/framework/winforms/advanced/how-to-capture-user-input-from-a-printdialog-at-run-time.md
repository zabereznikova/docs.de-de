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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937799"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="b7f52-102">Vorgehensweise: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b7f52-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="b7f52-103">Während Sie die Optionen in Bezug auf Drucken zur Entwurfszeit festlegen können, möchten Sie auch diese Optionen zur Laufzeit, wahrscheinlich aufgrund einer vom Benutzer vorgenommene Auswahl zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7f52-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="b7f52-104">Sie können Erfassen von Benutzereingaben zum Drucken von einem Dokument mithilfe der <xref:System.Windows.Forms.PrintDialog> und <xref:System.Drawing.Printing.PrintDocument> Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b7f52-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="b7f52-105">So ändern Sie die Druckoptionen programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b7f52-105">To change print options programmatically</span></span>  
  
1. <span data-ttu-id="b7f52-106">Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> und <xref:System.Drawing.Printing.PrintDocument> Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="b7f52-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="b7f52-107">Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft der <xref:System.Windows.Forms.PrintDialog> auf die <xref:System.Drawing.Printing.PrintDocument> zum Formular hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7f52-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. <span data-ttu-id="b7f52-108">Anzeigen der <xref:System.Windows.Forms.PrintDialog> -Komponente mithilfe der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b7f52-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. <span data-ttu-id="b7f52-109">Der Benutzer, die aus dem Dialogfeld ausgewählten Druckoptionen kopiert werden die <xref:System.Drawing.Printing.PrinterSettings> Eigenschaft der <xref:System.Drawing.Printing.PrintDocument> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b7f52-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f52-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7f52-110">See also</span></span>

- [<span data-ttu-id="b7f52-111">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f52-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="b7f52-112">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7f52-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
