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
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182008"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="02753-102">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="02753-102">User-Drawn Controls</span></span>
<span data-ttu-id="02753-103">Mit .NET Framework können Sie ganz einfach eigene Steuerelemente entwickeln.</span><span class="sxs-lookup"><span data-stu-id="02753-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="02753-104">Sie können ein Benutzersteuerelement erstellen, bei dem es sich um einen Satz von Standardsteuerelementen handelt, die durch Code miteinander verbunden sind, oder Sie können Ihr eigenes Steuerelement von Grund auf entwerfen.</span><span class="sxs-lookup"><span data-stu-id="02753-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="02753-105">Sie können sogar vererbung verwenden, um ein Steuerelement zu erstellen, das von einem vorhandenen Steuerelement erbt und seine inhärente Funktionalität ergänzt.</span><span class="sxs-lookup"><span data-stu-id="02753-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="02753-106">Unabhängig von der von Ihnen verfolgten Vorgehensweise bietet .NET Framework die Funktionalität zum Zeichnen einer benutzerdefinierten grafischen Benutzeroberfläche für jedes steuerelement, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="02753-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="02753-107">Das Malen eines Steuerelements erfolgt durch die <xref:System.Windows.Forms.Control.OnPaint%2A> Ausführung von Code in der Methode des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="02753-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="02753-108">Das einzelne Argument <xref:System.Windows.Forms.Control.OnPaint%2A> der <xref:System.Windows.Forms.PaintEventArgs> Methode ist ein Objekt, das alle Informationen und Funktionen bereitstellt, die zum Rendern des Steuerelements erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="02753-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="02753-109">Der <xref:System.Windows.Forms.PaintEventArgs> stellt als Eigenschaften zwei Hauptobjekte bereit, die beim Rendern des Steuerelements verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="02753-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="02753-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Objekt - das Rechteck, das den Teil des Steuerelements darstellt, der gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="02753-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="02753-111">Dies kann das gesamte Steuerelement oder ein Teil des Steuerelements sein, je nachdem, wie das Steuerelement gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="02753-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="02753-112"><xref:System.Drawing.Graphics>object - Kapselt mehrere grafikorientierte Objekte und Methoden, die die zum Zeichnen des Steuerelements erforderliche Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="02753-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="02753-113">Weitere Informationen zum <xref:System.Drawing.Graphics> Objekt und zur Verwendung finden Sie unter [Gewusst wie: Erstellen von Grafikobjekten für das Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="02753-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="02753-114">Das <xref:System.Windows.Forms.Control.OnPaint%2A> Ereignis wird ausgelöst, wenn das Steuerelement auf dem <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Bildschirm gezeichnet oder aktualisiert wird, und das Objekt stellt das Rechteck dar, in dem das Malen stattfindet.</span><span class="sxs-lookup"><span data-stu-id="02753-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="02753-115">Wenn das gesamte Steuerelement aktualisiert werden <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> muss, stellt der die Größe des gesamten Steuerelements dar.</span><span class="sxs-lookup"><span data-stu-id="02753-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="02753-116">Wenn jedoch nur ein Teil des Steuerelements <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> aktualisiert werden muss, stellt das Objekt nur den Bereich dar, der neu gezeichnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="02753-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="02753-117">Ein Beispiel für einen solchen Fall wäre, wenn ein Steuerelement teilweise durch ein anderes Steuerelement oder Formular in der Benutzeroberfläche verdeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="02753-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="02753-118">Beim Erben von der <xref:System.Windows.Forms.Control> Klasse müssen Sie <xref:System.Windows.Forms.Control.OnPaint%2A> die Methode überschreiben und innerhalb von Grafikrenderingcode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="02753-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="02753-119">Wenn Sie einem Benutzersteuerelement oder einem geerbten Steuerelement eine benutzerdefinierte grafische Benutzeroberfläche <xref:System.Windows.Forms.Control.OnPaint%2A> bereitstellen möchten, können Sie dies auch tun, indem Sie die Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="02753-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="02753-120">Unten ist ein Beispiel angegeben:</span><span class="sxs-lookup"><span data-stu-id="02753-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="02753-121">Im obigen Beispiel wird veranschaulicht, wie ein Steuerelement mit einer sehr einfachen grafischen Darstellung gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="02753-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="02753-122">Es ruft <xref:System.Windows.Forms.Control.OnPaint%2A> die Methode der Basisklasse <xref:System.Drawing.Pen> auf, es erstellt ein Objekt, mit dem gezeichnet <xref:System.Windows.Forms.Control.Location%2A> werden <xref:System.Windows.Forms.Control.Size%2A> soll, und zeichnet schließlich eine Ellipse im Rechteck, das durch das und des Steuerelements bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="02753-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="02753-123">Obwohl der größte Teil des Rendercodes wesentlich komplizierter ist, <xref:System.Drawing.Graphics> veranschaulicht dieses <xref:System.Windows.Forms.PaintEventArgs> Beispiel die Verwendung des im Objekt enthaltenen Objekts.</span><span class="sxs-lookup"><span data-stu-id="02753-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="02753-124">Beachten Sie, dass Sie die <xref:System.Windows.Forms.UserControl> <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.OnPaint%2A> Methode der Basisklasse nicht aufrufen sollten, wenn Sie von einer Klasse erben, die bereits über eine grafische Darstellung verfügt, z. B. oder , und diese Darstellung nicht in ihr Rendering integrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="02753-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="02753-125">Der Code <xref:System.Windows.Forms.Control.OnPaint%2A> in der Methode des Steuerelements wird ausgeführt, wenn das Steuerelement zum ersten Mal gezeichnet wird und wann immer es aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="02753-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="02753-126">Um sicherzustellen, dass das Steuerelement bei jeder Größenverwaltung neu gezeichnet wird, fügen Sie dem Konstruktor des Steuerelements die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="02753-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="02753-127">Verwenden <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> Sie die Eigenschaft, um ein nicht rechteckiges Steuerelement zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="02753-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02753-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02753-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="02753-129">Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="02753-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="02753-130">Konstituierende Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="02753-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="02753-131">Arten von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="02753-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
