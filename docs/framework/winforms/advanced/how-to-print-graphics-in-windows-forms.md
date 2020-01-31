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
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740642"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="5f9af-102">Gewusst wie: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f9af-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="5f9af-103">Häufig möchten Sie Grafiken in Ihrer Windows-basierten Anwendung drucken.</span><span class="sxs-lookup"><span data-stu-id="5f9af-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="5f9af-104">Die <xref:System.Drawing.Graphics>-Klasse stellt Methoden zum Zeichnen von Objekten für ein Gerät bereit, z. b. einen Bildschirm oder Drucker.</span><span class="sxs-lookup"><span data-stu-id="5f9af-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="5f9af-105">So drucken Sie Grafiken</span><span class="sxs-lookup"><span data-stu-id="5f9af-105">To print graphics</span></span>  
  
1. <span data-ttu-id="5f9af-106">Fügen Sie dem Formular eine <xref:System.Drawing.Printing.PrintDocument> Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="5f9af-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="5f9af-107">Verwenden Sie im <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignishandler die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>-Klasse, um den Drucker anzuweisen, welche Art von Grafiken gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f9af-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="5f9af-108">Das folgende Codebeispiel zeigt einen Ereignishandler, mit dem eine blaue Ellipse in einem umschließenden Rechteck erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5f9af-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="5f9af-109">Das Rechteck verfügt über die folgenden Speicherorte und Dimensionen: beginnend bei 100, 150 mit einer Breite von 250 und einer Höhe von 250.</span><span class="sxs-lookup"><span data-stu-id="5f9af-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="5f9af-110">(Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="5f9af-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f9af-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f9af-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="5f9af-112">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f9af-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
