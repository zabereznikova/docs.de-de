---
title: 'Vorgehensweise: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: fe937236332591f6065e618c49ca5cf2c54b987c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701221"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a><span data-ttu-id="9e462-102">Vorgehensweise: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="9e462-102">How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)</span></span>
<span data-ttu-id="9e462-103">Sie können das <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Steuerelement nutzen, um Kreise und Ovale auf einem Formular oder Container zu zeichnen, sowohl zur Entwurfszeit als auch zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="9e462-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control to draw circles or ovals on a form or container, both at design time and at run time.</span></span> <span data-ttu-id="9e462-104">Sie können das <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelement nutzen, um Quadrate, Rechtecke oder Rechtecke mit abgerundeten Ecken auf einem Formular oder Container zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="9e462-104">You can use the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control to draw squares, rectangles, or rectangles with rounded corners on a form or container.</span></span> <span data-ttu-id="9e462-105">Sie können dieses Steuerelement nutzen, um sowohl zur Entwurfszeit als auch zur Laufzeit Formen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="9e462-105">You can also use this control to draw shapes both at design time and at run time.</span></span>  
  
 <span data-ttu-id="9e462-106">Sie können die Darstellung einer Form durch Ändern der Breite, Farbe und Format des Rahmens anpassen.</span><span class="sxs-lookup"><span data-stu-id="9e462-106">You can customize the appearance of a shape by changing the width, color, and style of the border.</span></span> <span data-ttu-id="9e462-107">Der Hintergrund einer Form ist standardmäßig transparent; Sie können den Hintergrund zum Anzeigen einer durchgängigen Farbe, eines Musters, eines Farbverlaufs (Übergang von einer Farbe zu einer anderen) oder eines Bildes anpassen.</span><span class="sxs-lookup"><span data-stu-id="9e462-107">The background of a shape is transparent by default; you can customize the background to display a solid color, a pattern, a gradient fill (transitioning from one color to another), or an image.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a><span data-ttu-id="9e462-108">Zeichnen einer einfachen Form zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="9e462-108">To draw a simple shape at design time</span></span>  
  
1.  <span data-ttu-id="9e462-109">Ziehen Sie die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> oder <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte (finden Sie unter [Visual Basic Power Packs-Steuerelemente](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) in der **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9e462-109">Drag the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> or <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control from the **Visual Basic PowerPacks** tab (to install, see [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="9e462-110">Ziehen Sie den Zieh- und Zuschnittpunkt, um die Form in Position und Größe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9e462-110">Drag the sizing and move handles to size and position the shape.</span></span>  
  
     <span data-ttu-id="9e462-111">Sie können auch die Größe und position der Form durch Ändern der `Size` und `Position` Eigenschaften in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="9e462-111">You can also size and position the shape by changing the `Size` and `Position` properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="9e462-112">Um ein Rechteck mit abgerundeten Ecken zu erstellen, wählen Sie die `CornerRadius` -Eigenschaft in der **Eigenschaften** Fenster, und legen Sie ihn auf ein Wert, der größer als 0 ist.</span><span class="sxs-lookup"><span data-stu-id="9e462-112">To create a rectangle with rounded corners, select the `CornerRadius` property in the **Properties** window and set it to a value that is greater than 0.</span></span>  
  
3.  <span data-ttu-id="9e462-113">In der **Eigenschaften** optional weitere Eigenschaften fest, ändern Sie die Darstellung der Form-Fenster.</span><span class="sxs-lookup"><span data-stu-id="9e462-113">In the **Properties** window, optionally set additional properties to change the appearance of the shape.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a><span data-ttu-id="9e462-114">Zeichnen einer einfachen Form zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9e462-114">To draw a simple shape at run time</span></span>  
  
1.  <span data-ttu-id="9e462-115">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="9e462-115">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="9e462-116">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Microsoft.VisualBasic.PowerPacks.VS**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e462-116">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9e462-117">In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:</span><span class="sxs-lookup"><span data-stu-id="9e462-117">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="9e462-118">Fügen Sie den folgenden Code in ein `Event`-Verfahren ein:</span><span class="sxs-lookup"><span data-stu-id="9e462-118">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a><span data-ttu-id="9e462-119">Anpassen von Formen</span><span class="sxs-lookup"><span data-stu-id="9e462-119">Customizing Shapes</span></span>  
 <span data-ttu-id="9e462-120">Wenn Sie die Standardeinstellungen verwenden, werden die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>-Steuerelemente mit einem durchgehenden schwarzen Rahmen mit einem Pixel Breite und einem transparenten Hintergrund angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e462-120">When you use the default settings, the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls are displayed with a solid black border that is one pixel wide and a transparent background.</span></span> <span data-ttu-id="9e462-121">Sie können Breite, Stil und Farbe des Rahmens ändern, indem Sie Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="9e462-121">You can change the width, style, and color of the border by setting properties.</span></span> <span data-ttu-id="9e462-122">Zusätzliche Eigenschaften ermöglichen Ihnen, den Hintergrund einer Form zu einer Volltonfarbe, einem Muster, Farbverlauf oder einem Bild zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9e462-122">Additional properties enable you to change the background of a shape to a solid color, a pattern, a gradient fill, or an image.</span></span>  
  
 <span data-ttu-id="9e462-123">Bevor Sie den Hintergrund einer Form ändern, sollten Sie wissen, wie einige der Eigenschaften interagieren.</span><span class="sxs-lookup"><span data-stu-id="9e462-123">Before you change the background of a shape, you should know how several of the properties interact.</span></span>  
  
-   <span data-ttu-id="9e462-124">Die Einstellung der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>-Eigenschaft hat nur Auswirkungen, wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9e462-124">The <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> property setting has no effect unless the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="9e462-125">Wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> festgelegt ist, setzt <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="9e462-125">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> overrides the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span></span>  
  
-   <span data-ttu-id="9e462-126">Wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>-Eigenschaft auf einen Musterwert wie <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> oder <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical> festgelegt ist, wird das Muster in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> erscheinen.</span><span class="sxs-lookup"><span data-stu-id="9e462-126">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to a pattern value such as <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> or <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, the pattern will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span></span> <span data-ttu-id="9e462-127">Der Hintergrund erscheint in der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, sofern die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9e462-127">The background will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, provided that the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="9e462-128">Um eine graduelle Füllung anzuzeigen, muss die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> festgelegt werden und die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A>-Eigenschaft darf nicht auf <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9e462-128">In order to display a gradient fill, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property must be set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> and the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> property must be set to a value other than <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span></span>  
  
-   <span data-ttu-id="9e462-129">Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A>-Eigenschaft eines Bildes überschreibt alle anderen Hintergrundeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9e462-129">Setting the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> property to an image overrides all other background settings.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a><span data-ttu-id="9e462-130">Zeichnen eines Kreises mit einem benutzerdefinierten Rahmen</span><span class="sxs-lookup"><span data-stu-id="9e462-130">To draw a circle that has a custom border</span></span>  
  
1.  <span data-ttu-id="9e462-131">Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9e462-131">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="9e462-132">In der **Eigenschaften** Fenster in der `Size` Eigenschaftensatz, `Height` und `Width` auf die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="9e462-132">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="9e462-133">Legen Sie bei der Eigenschaft `BorderColor` die gewünschte Farbe fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-133">Set the `BorderColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="9e462-134">Legen Sie für die `BorderStyle`-Eigenschaft einen anderen Wert als `Solid` fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-134">Set the `BorderStyle` property to any value other than `Solid`.</span></span>  
  
5.  <span data-ttu-id="9e462-135">Legen Sie für `BorderWidth` die von Ihnen gewünschte Größe in Pixeln fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-135">Set the `BorderWidth` to the size that you want, in pixels.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a><span data-ttu-id="9e462-136">Zeichnen eines Kreises mit einer einfarbigen Füllung</span><span class="sxs-lookup"><span data-stu-id="9e462-136">To draw a circle that has a solid fill</span></span>  
  
1.  <span data-ttu-id="9e462-137">Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9e462-137">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="9e462-138">In der **Eigenschaften** Fenster in der `Size` Eigenschaftensatz, `Height` und `Width` auf die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="9e462-138">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="9e462-139">Legen Sie bei der Eigenschaft `BackColor` die gewünschte Farbe fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-139">Set the `BackColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="9e462-140">Legen Sie die `BackStyle`-Eigenschaft auf `Opaque` fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-140">Set the `BackStyle` property to `Opaque`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a><span data-ttu-id="9e462-141">Zeichnen eines Kreises mit einer gemusterten Füllung</span><span class="sxs-lookup"><span data-stu-id="9e462-141">To draw a circle that has a patterned fill</span></span>  
  
1.  <span data-ttu-id="9e462-142">Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9e462-142">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="9e462-143">In der **Eigenschaften** Fenster in der `Size` Eigenschaftensatz, `Height` und `Width` auf die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="9e462-143">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="9e462-144">Legen Sie für die `BackColor`-Eigenschaft die Farbe fest, die Sie für den Hintergrund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9e462-144">Set the `BackColor` property to the color that you want for the background.</span></span>  
  
4.  <span data-ttu-id="9e462-145">Legen Sie die `BackStyle`-Eigenschaft auf `Opaque` fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-145">Set the `BackStyle` property to `Opaque`.</span></span>  
  
5.  <span data-ttu-id="9e462-146">Legen Sie für die `FillColor`-Eigenschaft die Farbe fest, die Sie für das Muster festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="9e462-146">Set the `FillColor` property to the color that you want for the pattern.</span></span>  
  
6.  <span data-ttu-id="9e462-147">Legen Sie für die `FillStyle`-Eigenschaft einen beliebigen Wert fest, der weder `Transparent` noch `Solid` beträgt.</span><span class="sxs-lookup"><span data-stu-id="9e462-147">Set the `FillStyle` property to any value other than `Transparent` or `Solid`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a><span data-ttu-id="9e462-148">Zeichnen eines Kreises mit gradueller Füllung</span><span class="sxs-lookup"><span data-stu-id="9e462-148">To draw a circle that has a gradient fill</span></span>  
  
1.  <span data-ttu-id="9e462-149">Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9e462-149">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="9e462-150">In der **Eigenschaften** Fenster in der `Size` Eigenschaftensatz, `Height` und `Width` auf die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="9e462-150">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="9e462-151">Legen Sie für die `FillColor`-Eigenschaft die als Anfangsfarbe gewünschte Farbe fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-151">Set the `FillColor` property to the color that you want for the starting color.</span></span>  
  
4.  <span data-ttu-id="9e462-152">Legen Sie für die `FillGradientColor`-Eigenschaft die als Endfarbe gewünschte Farbe fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-152">Set the `FillGradientColor` property to the color that you want for the ending color.</span></span>  
  
5.  <span data-ttu-id="9e462-153">Legen Sie für die `FillGradientStyle` -Eigenschaft einen Wert fest, der nicht `None` fest.</span><span class="sxs-lookup"><span data-stu-id="9e462-153">Set the `FillGradientStyle` property to a value other than `None`.</span></span>  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a><span data-ttu-id="9e462-154">Zeichnen eines Kreises, der mit einem Bild gefüllt ist</span><span class="sxs-lookup"><span data-stu-id="9e462-154">To draw a circle that is filled with an image</span></span>  
  
1.  <span data-ttu-id="9e462-155">Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="9e462-155">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="9e462-156">In der **Eigenschaften** Fenster in der `Size` Eigenschaftensatz, `Height` und `Width` auf die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="9e462-156">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="9e462-157">Wählen Sie die `BackgroundImage` -Eigenschaft, und klicken Sie auf die **Auslassungspunkte** Schaltfläche (…).</span><span class="sxs-lookup"><span data-stu-id="9e462-157">Select the `BackgroundImage` property and click the **ellipsis** button (...).</span></span>  
  
4.  <span data-ttu-id="9e462-158">In der **Ressource auswählen** (Dialogfeld), wählen Sie eine anzuzeigende Bild.</span><span class="sxs-lookup"><span data-stu-id="9e462-158">In the **Select Resource** dialog box, select an image to display.</span></span> <span data-ttu-id="9e462-159">Wenn keine Bildressourcen aufgeführt sind, klicken Sie auf **Import** , um den Speicherort eines Bilds zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9e462-159">If no image resources are listed, click **Import** to browse to the location of an image.</span></span>  
  
5.  <span data-ttu-id="9e462-160">Klicken Sie auf **OK** um das Bild einzufügen.</span><span class="sxs-lookup"><span data-stu-id="9e462-160">Click **OK** to insert the image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e462-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e462-161">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>
- <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>
- [<span data-ttu-id="9e462-162">Einführung in das Line-Steuerelement und das Shape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9e462-162">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [<span data-ttu-id="9e462-163">Vorgehensweise: Zeichnen von Linien mit dem LineShape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9e462-163">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
