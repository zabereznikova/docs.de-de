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
ms.openlocfilehash: 26b4f062c120bf543a5e597fc8c734e8cc336bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542196"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="75ded-102">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="75ded-102">User-Drawn Controls</span></span>
<span data-ttu-id="75ded-103">.NET Framework bietet die Möglichkeit, eigene Steuerelemente entwickeln.</span><span class="sxs-lookup"><span data-stu-id="75ded-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="75ded-104">Können Sie ein Benutzersteuerelement, das einen Satz von Standardsteuerelementen zusammen in Code vorgesehen ist, erstellen, oder Sie können ein eigenes Steuerelement von Grund auf neu entwerfen, einrichten.</span><span class="sxs-lookup"><span data-stu-id="75ded-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="75ded-105">Sie können sogar Vererbung verwenden, erstellen ein Steuerelement, das von einem vorhandenen Steuerelement erbt und dessen implementierte Funktionalität hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75ded-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="75ded-106">Welchen Ansatz Sie verwenden, stellt .NET Framework die Funktionalität, um eine benutzerdefinierte grafische Benutzeroberfläche für jedes Steuerelement gezeichnet werden soll, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="75ded-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="75ded-107">Zeichnen eines Steuerelements wird erreicht, indem die Ausführung von Code in des Steuerelements <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="75ded-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="75ded-108">Das Argument der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode ist ein <xref:System.Windows.Forms.PaintEventArgs> Objekt, das alle Informationen und zum Rendern des Steuerelements erforderliche Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="75ded-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="75ded-109">Die <xref:System.Windows.Forms.PaintEventArgs> zwei principal-Objekte, die beim Rendern des Steuerelements verwendet werden, als Eigenschaften bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="75ded-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
-   <span data-ttu-id="75ded-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt – das Rechteck, das den Teil des Steuerelements darstellt, die gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="75ded-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="75ded-111">Dies kann das gesamte Steuerelement oder einen Teil des Steuerelements abhängig davon, wie das Steuerelement gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="75ded-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
-   <span data-ttu-id="75ded-112"><xref:System.Drawing.Graphics> Objekt - kapselt mehrere Graphics-orientierten Objekte und Methoden, die zum Zeichnen des Steuerelements erforderliche Funktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75ded-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="75ded-113">Weitere Informationen zu den <xref:System.Drawing.Graphics> -Objekt und zum verwenden, finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="75ded-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="75ded-114">Die <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis wird ausgelöst, wenn das Steuerelement gezeichnet oder auf dem Bildschirm aktualisiert wird und die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt darstellt, das Rechteck, in dem gezeichnet werden stattfinden.</span><span class="sxs-lookup"><span data-stu-id="75ded-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="75ded-115">Wenn das gesamte Steuerelement aktualisiert werden, werden muss die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> wird die Größe des gesamten Steuerelements darstellen.</span><span class="sxs-lookup"><span data-stu-id="75ded-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="75ded-116">Wenn nur ein Teil des Steuerelements muss aktualisiert werden, werden jedoch die <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Objekt repräsentiert nur den Bereich mit der neu gezeichnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="75ded-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="75ded-117">Ein Beispiel der Fall wäre, wenn ein Steuerelement von einem anderen Steuerelement oder ein Formular in der Benutzeroberfläche teilweise verdeckt werden wurde.</span><span class="sxs-lookup"><span data-stu-id="75ded-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="75ded-118">Beim Erben von der <xref:System.Windows.Forms.Control> -Klasse, die Sie überschreiben müssen die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, und geben Sie Code zum Rendern der Grafiken.</span><span class="sxs-lookup"><span data-stu-id="75ded-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="75ded-119">Wenn Sie eine benutzerdefinierte grafische Benutzeroberfläche für ein benutzerdefiniertes Steuerelement oder ein geerbtes Steuerelement bereitstellen möchten, können Sie auch dies tun durch Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="75ded-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="75ded-120">Ein Beispiel ist unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="75ded-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="75ded-121">Im vorherige Beispiel veranschaulicht, wie ein Steuerelement mit einer sehr einfachen grafischen Darstellung gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="75ded-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="75ded-122">Aufruft der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der Basisklasse er erstellt eine <xref:System.Drawing.Pen> -Objekt mit dem gezeichnet werden soll, und schließlich zeichnet eine Ellipse, die in dem Rechteck, bestimmt durch die <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Size%2A> des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="75ded-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="75ded-123">Obwohl die meisten Renderingcodes deutlich komplizierter als das sein wird, wird dieses Beispiel veranschaulicht die Verwendung von der <xref:System.Drawing.Graphics> Objekt in der <xref:System.Windows.Forms.PaintEventArgs> Objekt.</span><span class="sxs-lookup"><span data-stu-id="75ded-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="75ded-124">Beachten Sie, dass, wenn Sie von einer Klasse erben, die bereits eine grafische Darstellung, wie z. B. <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Button>, und Sie nicht diese Darstellung in das Rendering integrieren möchten, rufen Sie nicht die Basisklasse <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="75ded-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="75ded-125">Der Code in der <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode des Steuerelements wird ausgeführt, wenn das Steuerelement zuerst gezeichnet wird, und wenn sie aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="75ded-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="75ded-126">Um sicherzustellen, dass das Steuerelement neu gezeichnet wird jedes Mal, wenn er geändert wird, fügen Sie an den Konstruktor des Steuerelements die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="75ded-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="75ded-127">Verwenden der <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> Eigenschaft, um ein viereckig Steuerelement zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="75ded-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ded-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75ded-128">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [<span data-ttu-id="75ded-129">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="75ded-129">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="75ded-130">Konstituierende Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="75ded-130">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [<span data-ttu-id="75ded-131">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="75ded-131">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
