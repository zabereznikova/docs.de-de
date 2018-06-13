---
title: Überschreiben der OnPaint-Methode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: fc41158e9a3d5d331b391f0f28701612012becf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537215"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="bc0d3-102">Überschreiben der OnPaint-Methode</span><span class="sxs-lookup"><span data-stu-id="bc0d3-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="bc0d3-103">Die grundlegenden Schritte zum Überschreiben von Ereignissen definiert, der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] identisch sind und in der folgenden Liste zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="bc0d3-104">Überschreiben ein geerbtes Ereignisses</span><span class="sxs-lookup"><span data-stu-id="bc0d3-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="bc0d3-105">Überschreiben Sie die geschützte `On` *EventName* Methode.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="bc0d3-106">Rufen Sie die `On` *EventName* -Methode der Basisklasse, von der überschriebenen `On` *EventName* Methode, damit registrierte Delegaten das Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="bc0d3-107">Die <xref:System.Windows.Forms.Control.Paint> Ereignis wird im folgenden ausführlich erläutert, da jedes Windows Forms-Steuerelement überschreiben, muss die <xref:System.Windows.Forms.Control.Paint> Ereignis, das von der erbt <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="bc0d3-108">Die Basis <xref:System.Windows.Forms.Control> Klasse weiß nicht, wie ein abgeleitetes Steuerelement gezeichnet werden muss und keine Zeichnungslogik in die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="bc0d3-109">Die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode <xref:System.Windows.Forms.Control> einfach verteilt die <xref:System.Windows.Forms.Control.Paint> Ereignis registrierten Ereignisempfänger.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="bc0d3-110">Wenn Sie das Beispiel in durchgearbeitet [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), Sie haben gelernt, dass ein Beispiel zum Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="bc0d3-111">Das folgende Codefragment stammt aus dem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-111">The following code fragment is taken from that sample.</span></span>  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <span data-ttu-id="bc0d3-112">Die <xref:System.Windows.Forms.PaintEventArgs> Klasse enthält Daten für die <xref:System.Windows.Forms.Control.Paint> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="bc0d3-113">Er verfügt über zwei Eigenschaften, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-113">It has two properties, as shown in the following code.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <span data-ttu-id="bc0d3-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ist das Rechteck gezeichnet werden, und die <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft bezieht sich auf eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="bc0d3-115">Die Klassen in der <xref:System.Drawing?displayProperty=nameWithType> Namespace sind verwaltete Klassen, die Zugriff auf die Funktionalität bereitstellen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], die neue Windows-Grafikbibliothek.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="bc0d3-116">Die <xref:System.Drawing.Graphics> Objekt verfügt über Methoden, die Punkte, Zeichenfolgen, Linien, Bögen, Ellipsen und vielen anderen Formen gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="bc0d3-117">Ein Steuerelement ruft seine <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode auf, wenn sie die visuelle Darstellung geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="bc0d3-118">Diese Methode löst wiederum die <xref:System.Windows.Forms.Control.Paint> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bc0d3-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0d3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc0d3-119">See Also</span></span>  
 [<span data-ttu-id="bc0d3-120">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bc0d3-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="bc0d3-121">Wiedergeben eines Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="bc0d3-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="bc0d3-122">Definieren eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="bc0d3-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
