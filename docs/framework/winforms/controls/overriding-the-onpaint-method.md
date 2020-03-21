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
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182035"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="7769b-102">Überschreiben der OnPaint-Methode</span><span class="sxs-lookup"><span data-stu-id="7769b-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="7769b-103">Die grundlegenden Schritte zum Überschreiben eines in .NET Framework definierten Ereignisses sind identisch und werden in der folgenden Liste zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="7769b-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="7769b-104">So überschreiben Sie ein geerbtes Ereignis</span><span class="sxs-lookup"><span data-stu-id="7769b-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="7769b-105">Überschreiben Sie `On`die geschützte *EventName-Methode.*</span><span class="sxs-lookup"><span data-stu-id="7769b-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="7769b-106">Rufen `On`Sie die *EventName-Methode* der `On`Basisklasse aus der überschriebenen *EventName-Methode* auf, damit registrierte Delegaten das Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="7769b-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="7769b-107">Das <xref:System.Windows.Forms.Control.Paint> Ereignis wird hier ausführlich erläutert, da jedes <xref:System.Windows.Forms.Control.Paint> Windows Forms-Steuerelement <xref:System.Windows.Forms.Control>das Ereignis überschreiben muss, von dem es erbt.</span><span class="sxs-lookup"><span data-stu-id="7769b-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="7769b-108">Die <xref:System.Windows.Forms.Control> Basisklasse weiß nicht, wie ein abgeleitetes Steuerelement gezeichnet werden <xref:System.Windows.Forms.Control.OnPaint%2A> muss, und stellt keine Mallogik in der Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="7769b-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="7769b-109">Die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, <xref:System.Windows.Forms.Control> das <xref:System.Windows.Forms.Control.Paint> Ereignis einfach an registrierte Ereignisempfänger zu senden.</span><span class="sxs-lookup"><span data-stu-id="7769b-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="7769b-110">Wenn Sie das Beispiel unter [Gewusst wie: Entwickeln eines einfachen Windows Forms](how-to-develop-a-simple-windows-forms-control.md) <xref:System.Windows.Forms.Control.OnPaint%2A> Control verarbeitet haben, haben Sie ein Beispiel für das Überschreiben der Methode gesehen.</span><span class="sxs-lookup"><span data-stu-id="7769b-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="7769b-111">Das folgende Codefragment wird diesem Beispiel entnommen.</span><span class="sxs-lookup"><span data-stu-id="7769b-111">The following code fragment is taken from that sample.</span></span>  
  
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
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 <span data-ttu-id="7769b-112">Die <xref:System.Windows.Forms.PaintEventArgs> Klasse enthält <xref:System.Windows.Forms.Control.Paint> Daten für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7769b-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="7769b-113">Es hat zwei Eigenschaften, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7769b-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="7769b-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>ist das rechteckige Rechteck, <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> das gezeichnet <xref:System.Drawing.Graphics> werden soll, und die Eigenschaft bezieht sich auf ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="7769b-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="7769b-115">Die Klassen <xref:System.Drawing?displayProperty=nameWithType> im Namespace sind verwaltete Klassen, die Zugriff auf die Funktionalität von GDI+, der neuen Windows-Grafikbibliothek, bieten.</span><span class="sxs-lookup"><span data-stu-id="7769b-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="7769b-116">Das <xref:System.Drawing.Graphics> Objekt verfügt über Methoden zum Zeichnen von Punkten, Zeichenfolgen, Linien, Bogen, Ellipsen und vielen anderen Formen.</span><span class="sxs-lookup"><span data-stu-id="7769b-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="7769b-117">Ein Steuerelement ruft <xref:System.Windows.Forms.Control.OnPaint%2A> seine Methode auf, wenn es seine visuelle Anzeige ändern muss.</span><span class="sxs-lookup"><span data-stu-id="7769b-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="7769b-118">Diese Methode wiederum <xref:System.Windows.Forms.Control.Paint> löst das Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="7769b-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7769b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7769b-119">See also</span></span>

- [<span data-ttu-id="7769b-120">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7769b-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="7769b-121">Wiedergeben eines Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="7769b-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="7769b-122">Definieren eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7769b-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
