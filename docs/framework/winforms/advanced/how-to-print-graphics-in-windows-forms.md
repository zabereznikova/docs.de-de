---
title: 'Gewusst wie: Drucken von Grafiken in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9c18f563cfd1ab15740ea773effefd89206eb0a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="d9ee7-102">Gewusst wie: Drucken von Grafiken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9ee7-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="d9ee7-103">In vielen Fällen sollten Sie das Drucken von Grafiken in der Windows-basierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="d9ee7-104">Die <xref:System.Drawing.Graphics> -Klasse stellt Methoden zum Zeichnen von Objekten auf einem Gerät, z. B. einem Bildschirm oder Drucker.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="d9ee7-105">Zum Drucken von Grafiken</span><span class="sxs-lookup"><span data-stu-id="d9ee7-105">To print graphics</span></span>  
  
1.  <span data-ttu-id="d9ee7-106">Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> -Komponente in Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="d9ee7-107">In der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler der <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft von der <xref:System.Drawing.Printing.PrintPageEventArgs> Klasse weisen Sie den Drucker, auf welche Art von Grafiken zum Drucken an.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="d9ee7-108">Das folgende Codebeispiel zeigt einen Ereignishandler verwendet, um eine blaue Ellipse in ein umschließendes Rechteck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="d9ee7-109">Das Rechteck hat die folgenden Speicherort und Dimensionen: beginnend bei 100, 150 mit einer Breite von 250 und eine Höhe von 250.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="d9ee7-110">(Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d9ee7-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9ee7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9ee7-111">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="d9ee7-112">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9ee7-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
