---
title: Benutzerdefinierte Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: 50036f5bef323368b4970a080ca7a70cf94252d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966483"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="0f848-102">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0f848-102">User-Drawn Controls</span></span>
<span data-ttu-id="0f848-103">Der .NET Framework bietet Ihnen die Möglichkeit, ihre eigenen Steuerelemente auf einfache Weise zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="0f848-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="0f848-104">Sie können ein Benutzer Steuerelement erstellen, bei dem es sich um einen Satz von Standard Steuerelementen handelt, die durch Code verbunden sind, oder Sie können ein eigenes Steuerelement von Grund auf entwerfen.</span><span class="sxs-lookup"><span data-stu-id="0f848-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="0f848-105">Sie können sogar Vererbung verwenden, um ein Steuerelement zu erstellen, das von einem vorhandenen Steuerelement erbt und seine inhärente Funktionalität hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0f848-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="0f848-106">Der .NET Framework stellt die Funktionalität bereit, um eine benutzerdefinierte grafische Oberfläche für jedes von Ihnen erstellte Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="0f848-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="0f848-107">Das Zeichnen eines Steuer Elements wird durch die Ausführung von Code in der- <xref:System.Windows.Forms.Control.OnPaint%2A> Methode des Steuer Elements erreicht.</span><span class="sxs-lookup"><span data-stu-id="0f848-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0f848-108">Das einzige Argument der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode ist ein <xref:System.Windows.Forms.PaintEventArgs> -Objekt, das alle Informationen und Funktionen bereitstellt, die zum Rendering des Steuer Elements erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0f848-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="0f848-109">Die <xref:System.Windows.Forms.PaintEventArgs> stellt als Eigenschaften zwei Prinzipal Objekte zur Verfügung, die beim Rendering des Steuer Elements verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0f848-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="0f848-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Object: das Rechteck, das den Teil des-Steuer Elements darstellt, der gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="0f848-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="0f848-111">Dies kann das gesamte Steuerelement oder ein Teil des Steuer Elements sein, je nachdem, wie das Steuerelement gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="0f848-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="0f848-112"><xref:System.Drawing.Graphics>Object: kapselt verschiedene Grafik orientierte Objekte und Methoden, die die Funktionalität bereitstellen, die zum Zeichnen des Steuer Elements erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0f848-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="0f848-113">Weitere Informationen <xref:System.Drawing.Graphics> zum Objekt und seiner Verwendung finden [Sie unter Gewusst wie: Erstellen Sie Grafik Objekte zum](../advanced/how-to-create-graphics-objects-for-drawing.md)zeichnen.</span><span class="sxs-lookup"><span data-stu-id="0f848-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="0f848-114">Das <xref:System.Windows.Forms.Control.OnPaint%2A> -Ereignis wird ausgelöst, wenn das-Steuerelement auf dem Bildschirm gezeichnet oder <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> aktualisiert wird, und das-Objekt stellt das Rechteck dar, in dem das Zeichnen stattfinden soll.</span><span class="sxs-lookup"><span data-stu-id="0f848-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="0f848-115">Wenn das gesamte Steuerelement aktualisiert werden muss, stellt <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> die Größe des gesamten Steuer Elements dar.</span><span class="sxs-lookup"><span data-stu-id="0f848-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="0f848-116">Wenn nur ein Teil des Steuer Elements aktualisiert werden muss, stellt das <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt jedoch nur den Bereich dar, der neu gezeichnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="0f848-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="0f848-117">Ein Beispiel für einen solchen Fall wäre, wenn ein Steuerelement teilweise von einem anderen Steuerelement oder Formular in der Benutzeroberfläche verdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="0f848-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="0f848-118">Wenn Sie von der <xref:System.Windows.Forms.Control> -Klasse erben, müssen Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode überschreiben und Grafik Rendering-Code in bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f848-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="0f848-119">Wenn Sie eine benutzerdefinierte grafische Oberfläche für ein Benutzer Steuerelement oder ein geerbtes Steuerelement bereitstellen möchten, können Sie <xref:System.Windows.Forms.Control.OnPaint%2A> auch die-Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0f848-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0f848-120">Unten ist ein Beispiel angegeben:</span><span class="sxs-lookup"><span data-stu-id="0f848-120">An example is shown below:</span></span>  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 <span data-ttu-id="0f848-121">Im vorangehenden Beispiel wird veranschaulicht, wie ein-Steuerelement mit einer sehr einfachen grafischen Darstellung dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f848-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="0f848-122">Sie ruft die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse auf, erstellt ein <xref:System.Drawing.Pen> -Objekt, mit dem gezeichnet werden soll, und zeichnet schließlich eine Ellipse in dem Rechteck <xref:System.Windows.Forms.Control.Location%2A> , <xref:System.Windows.Forms.Control.Size%2A> das von der und des-Steuer Elements bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="0f848-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="0f848-123">Obwohl der größte Renderingcode deutlich komplizierter ist als dieser, wird <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> in diesem Beispiel die Verwendung des-Objekts veranschaulicht, das im-Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0f848-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="0f848-124">Beachten Sie Folgendes: Wenn Sie von einer Klasse erben, die bereits über eine grafische Darstellung verfügt, <xref:System.Windows.Forms.UserControl> z <xref:System.Windows.Forms.Button>. b. oder, und Sie diese Darstellung nicht in das Rendering einbinden möchten, sollten Sie nicht die <xref:System.Windows.Forms.Control.OnPaint%2A> Basisklasse anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0f848-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="0f848-125">Der Code in der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode des-Steuer Elements wird ausgeführt, wenn das Steuerelement zum ersten Mal gezeichnet wird, und wenn es aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f848-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="0f848-126">Fügen Sie dem Konstruktor des Steuer Elements die folgende Zeile hinzu, um sicherzustellen, dass das Steuerelement jedes Mal neu gezeichnet wird, wenn die Größe geändert wird:</span><span class="sxs-lookup"><span data-stu-id="0f848-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="0f848-127">Verwenden Sie <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> die-Eigenschaft zum Implementieren eines nicht rechteckigen Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="0f848-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f848-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f848-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="0f848-129">Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="0f848-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="0f848-130">Konstituierende Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0f848-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="0f848-131">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="0f848-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
