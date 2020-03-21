---
title: 'Gewusst wie: Drucken von Grafiken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182535"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="4230a-102">Gewusst wie: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4230a-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="4230a-103">Häufig sollten Sie Grafiken in Ihrer Windows-basierten Anwendung drucken.</span><span class="sxs-lookup"><span data-stu-id="4230a-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="4230a-104">Die <xref:System.Drawing.Graphics> Klasse stellt Methoden zum Zeichnen von Objekten auf einem Gerät bereit, z. B. auf einem Bildschirm oder Drucker.</span><span class="sxs-lookup"><span data-stu-id="4230a-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="4230a-105">So drucken Sie Grafiken</span><span class="sxs-lookup"><span data-stu-id="4230a-105">To print graphics</span></span>  
  
1. <span data-ttu-id="4230a-106">Fügen <xref:System.Drawing.Printing.PrintDocument> Sie dem Formular eine Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="4230a-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="4230a-107">Verwenden <xref:System.Drawing.Printing.PrintDocument.PrintPage> Sie im Ereignishandler <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> die <xref:System.Drawing.Printing.PrintPageEventArgs> Eigenschaft der Klasse, um den Drucker anzuweisen, welche Art von Grafiken gedruckt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4230a-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="4230a-108">Das folgende Codebeispiel zeigt einen Ereignishandler, der zum Erstellen einer blauen Ellipse innerhalb eines angrenzenden Rechtecks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4230a-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="4230a-109">Das Rechteck hat die folgende Position und Abmessungen: beginnend bei 100, 150 mit einer Breite von 250 und einer Höhe von 250.</span><span class="sxs-lookup"><span data-stu-id="4230a-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="4230a-110">(Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4230a-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4230a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4230a-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="4230a-112">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4230a-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
