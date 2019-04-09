---
title: 'Vorgehensweise: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: e3d1c2b681e98dc7c45467683924dd4022eb377e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094033"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="de263-102">Vorgehensweise: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de263-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="de263-103">Wenn Sie eine einfache Grafik animieren, können Benutzer manchmal Flimmern oder andere unerwünschte visuelle Effekte auftreten.</span><span class="sxs-lookup"><span data-stu-id="de263-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="de263-104">Eine Möglichkeit zum Beschränken dieses Problems ist, einen "Bitblt" auf die Grafik verwenden.</span><span class="sxs-lookup"><span data-stu-id="de263-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="de263-105">BitBlt ist die "Bitblocktransfer" der Farbdaten aus einem Ursprung Rechteck aus Pixeln einen Ziel-Rechteck aus Pixeln.</span><span class="sxs-lookup"><span data-stu-id="de263-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="de263-106">Mit Windows Forms, Bitblt erfolgt mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="de263-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="de263-107">In den Parametern der Methode geben Sie an der Quelle und Ziel (als Punkt), die Größe des Bereichs für den kopiert werden und das Graphics-Objekt verwendet, um die neue Form zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="de263-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="de263-108">Im folgenden Beispiel wird eine Form gezeichnet wird, auf dem Formular in der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="de263-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="de263-109">Anschließend wird die <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode wird verwendet, um die Form zu duplizieren.</span><span class="sxs-lookup"><span data-stu-id="de263-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de263-110">Festlegen des Formulars <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true` veranlasst grafikbasierte-Code in die <xref:System.Windows.Forms.Control.Paint> Ereignis werden doppelt gepufferte.</span><span class="sxs-lookup"><span data-stu-id="de263-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="de263-111">Obwohl dies nicht über aller erkennbaren Leistungsgewinne besitzt, wenn Sie den folgenden Code verwenden, ist es etwas zu bedenken, bei der Arbeit mit komplexeren grafikbearbeitung Code.</span><span class="sxs-lookup"><span data-stu-id="de263-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de263-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de263-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de263-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="de263-113">Compiling the Code</span></span>  
 <span data-ttu-id="de263-114">Der obige Code ausgeführt wird, in der Form <xref:System.Windows.Forms.Control.Paint> -Ereignishandler so, dass die Grafiken erhalten bleiben, wenn das Formular neu gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="de263-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="de263-115">Rufen Sie daher nicht Grafiken bezogene Methoden in der <xref:System.Windows.Forms.Form.Load> -Ereignishandler, da der gezeichnete Inhalt nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="de263-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de263-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de263-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="de263-117">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de263-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="de263-118">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="de263-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
