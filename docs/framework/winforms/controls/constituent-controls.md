---
title: Konstituierende Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 6fb708b81089b4fcd3678b35d1bcf7da2244c6d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525561"
---
# <a name="constituent-controls"></a><span data-ttu-id="12c43-102">Konstituierende Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="12c43-102">Constituent Controls</span></span>
<span data-ttu-id="12c43-103">Die Steuerelemente, aus denen ein Benutzersteuerelement gebildet wird, werden als *konstituierende Steuerelemente* bezeichnet. Sie verhalten sich beim Rendering benutzerdefinierter Grafiken relativ unflexibel.</span><span class="sxs-lookup"><span data-stu-id="12c43-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="12c43-104">Alle Windows Forms-Steuerelementen behandeln, ihre eigenen Rendering über ihre eigenen <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="12c43-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="12c43-105">Da diese Methode geschützt ist, kann der Entwickler nicht auf sie zugreifen. Daher kann nicht verhindert werden, dass die Methode ausgeführt wird, sobald ein Steuerelement gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="12c43-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="12c43-106">Das bedeutet jedoch nicht, dass kein Code hinzugefügt werden kann, um die Darstellung konstituierender Steuerelemente zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="12c43-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="12c43-107">Zusätzliches Rendering kann ermöglicht werden, indem ein Ereignishandler hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="12c43-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="12c43-108">Nehmen wir beispielsweise an, die Sie erstellen eine <xref:System.Windows.Forms.UserControl> mit einer Schaltfläche mit dem Namen `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="12c43-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="12c43-109">Wenn Sie zusätzliche gerendert hinausgeht, was durch bereitgestellt wurde die <xref:System.Web.UI.WebControls.Button>, fügen Sie Code zum Benutzersteuerelement ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="12c43-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="12c43-110">Einige Windows Forms-Steuerelemente, z. B. <xref:System.Windows.Forms.TextBox>, direkt von Windows gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="12c43-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="12c43-111">In diesen Fällen die <xref:System.Windows.Forms.Control.OnPaint%2A> wird nie aufgerufen, und daher im obigen Beispiel wird nie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="12c43-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="12c43-112">Hierdurch wird eine Methode erstellt, die jedes Mal ausgeführt wird, sobald das `MyButton.Paint`-Ereignis ausgeführt wird. So wird dem Steuerelement eine zusätzliche grafische Darstellung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12c43-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="12c43-113">Beachten Sie, dass dadurch nicht die Ausführung von `MyButton.OnPaint` verhindert wird. Daher werden zusätzlich zu den benutzerdefinierten Zeichenvorgängen alle Zeichenvorgänge ausgeführt, die in der Regel über eine Schaltfläche erfolgen.</span><span class="sxs-lookup"><span data-stu-id="12c43-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="12c43-114">Einzelheiten zu GDI+-Technologie und benutzerdefiniertem Rendering finden Sie unter [Erstellen von Grafiken mit GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="12c43-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="12c43-115">Der beste Weg zum Erreichen einer einheitlichen Darstellung des Steuerelements besteht darin, ein geerbtes Steuerelement zu erstellen und Code zum benutzerdefinierten Ausgeben dieses Steuerelements zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="12c43-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="12c43-116">Einzelheiten dazu finden Sie unter [Benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span><span class="sxs-lookup"><span data-stu-id="12c43-116">For details, see [User-Drawn Controls](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c43-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12c43-117">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="12c43-118">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="12c43-118">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 [<span data-ttu-id="12c43-119">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="12c43-119">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="12c43-120">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="12c43-120">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
