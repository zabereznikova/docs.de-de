---
title: 'Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms'
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
ms.openlocfilehash: dc5f05ff4ea9f3c2b828cbe37860e1bd241fc604
ms.sourcegitcommit: 3d42e1d73e21c35c540dd4adbea23efcbe1b8b0a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "36270434"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="dbb1c-102">Gewusst wie: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dbb1c-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="dbb1c-103">Wenn Sie eine einfache Grafik animieren, können Benutzer manchmal Flackern oder andere unerwünschte visuelle Effekte auftreten.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="dbb1c-104">Eine Möglichkeit, dieses Problem zu beschränken ist, einen "Bitblt" auf die Grafik zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="dbb1c-105">BitBlt ist die "Bitblocktransfer" der Farbdaten aus einem Ursprung Rechteck aus Pixeln einen Ziel-Rechteck aus Pixeln.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="dbb1c-106">Mit Windows Forms Bitblt erfolgt mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="dbb1c-107">In den Parametern der Methode geben Sie an der Quelle und Ziel (als Punkte), die Größe des Bereichs, kopiert werden und die Graphics-Objekts verwendet, um die neue Form zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="dbb1c-108">Im folgenden Beispiel wird eine Form gezeichnet wird, auf dem Formular in seiner <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="dbb1c-109">Anschließend wird die <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode wird verwendet, um die Form zu duplizieren.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbb1c-110">Festlegen des Formulars <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true` stellen grafikbasierte Code in die <xref:System.Windows.Forms.Control.Paint> Ereignis werden doppelt gepuffert.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="dbb1c-111">Obwohl dies nicht über messbaren Leistungssteigerung besitzt, wenn Sie den folgenden Code verwenden, ist es etwas zu bedenken, bei der Arbeit mit komplexen grafikbearbeitung Code.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbb1c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbb1c-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="dbb1c-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="dbb1c-113">Compiling the Code</span></span>  
 <span data-ttu-id="dbb1c-114">Der obige Code ausgeführt wird, in der Form <xref:System.Windows.Forms.Control.Paint> -Ereignishandler, damit die Grafiken erhalten bleiben, wenn die Form neu gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="dbb1c-115">Rufen Sie daher keine Arbeit mit Grafiken und Methoden in der <xref:System.Windows.Forms.Form.Load> Ereignishandler, da der gezeichnete Inhalt nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="dbb1c-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb1c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbb1c-116">See Also</span></span>  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="dbb1c-117">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dbb1c-117">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="dbb1c-118">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="dbb1c-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
