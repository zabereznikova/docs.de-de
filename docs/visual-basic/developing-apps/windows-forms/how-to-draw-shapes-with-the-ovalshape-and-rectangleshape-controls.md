---
title: 'Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: f87865ba3aebe5739b87d6ae6bfeaa957af726d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592274"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a>Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement (Visual Studio)
Sie können das <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Steuerelement nutzen, um Kreise und Ovale auf einem Formular oder Container zu zeichnen, sowohl zur Entwurfszeit als auch zur Laufzeit. Sie können das <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelement nutzen, um Quadrate, Rechtecke oder Rechtecke mit abgerundeten Ecken auf einem Formular oder Container zu zeichnen. Sie können dieses Steuerelement nutzen, um sowohl zur Entwurfszeit als auch zur Laufzeit Formen zu zeichnen.  
  
 Sie können die Darstellung einer Form durch Ändern der Breite, Farbe und Format des Rahmens anpassen. Der Hintergrund einer Form ist standardmäßig transparent; Sie können den Hintergrund zum Anzeigen einer durchgängigen Farbe, eines Musters, eines Farbverlaufs (Übergang von einer Farbe zu einer anderen) oder eines Bildes anpassen.  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a>Zeichnen einer einfachen Form zur Entwurfszeit  
  
1.  Ziehen Sie die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> oder <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte (finden Sie unter [Visual Basic Power Packs-Steuerelemente](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) in der **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Ziehen Sie den Zieh- und Zuschnittpunkt, um die Form in Position und Größe zu ändern.  
  
     Sie können auch die Größe und position der Form durch Ändern der `Size` und `Position` Eigenschaften in der **Eigenschaften** Fenster.  
  
     Um ein Rechteck mit abgerundeten Ecken zu erstellen, wählen Sie die `CornerRadius` Eigenschaft in der **Eigenschaften** Fenster, und legen Sie es auf ein Wert, der größer als 0 ist.  
  
3.  In der **Eigenschaften** Fenster weitere Eigenschaften optional so ändern Sie die Darstellung der Form fest.  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a>Zeichnen einer einfachen Form zur Laufzeit  
  
1.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .  
  
2.  In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Microsoft.VisualBasic.PowerPacks.VS**, und klicken Sie dann auf **OK**.  
  
3.  In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Fügen Sie den folgenden Code in ein `Event`-Verfahren ein:  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a>Anpassen von Formen  
 Wenn Sie die Standardeinstellungen verwenden, werden die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>-Steuerelemente mit einem durchgehenden schwarzen Rahmen mit einem Pixel Breite und einem transparenten Hintergrund angezeigt. Sie können Breite, Stil und Farbe des Rahmens ändern, indem Sie Eigenschaften festlegen. Zusätzliche Eigenschaften ermöglichen Ihnen, den Hintergrund einer Form zu einer Volltonfarbe, einem Muster, Farbverlauf oder einem Bild zu ändern.  
  
 Bevor Sie den Hintergrund einer Form ändern, sollten Sie wissen, wie einige der Eigenschaften interagieren.  
  
-   Die Einstellung der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>-Eigenschaft hat nur Auswirkungen, wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> festgelegt ist.  
  
-   Wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> festgelegt ist, setzt <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> außer Kraft.  
  
-   Wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>-Eigenschaft auf einen Musterwert wie <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> oder <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical> festgelegt ist, wird das Muster in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> erscheinen. Der Hintergrund erscheint in der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, sofern die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> festgelegt ist.  
  
-   Um eine graduelle Füllung anzuzeigen, muss die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> festgelegt werden und die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A>-Eigenschaft darf nicht auf <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None> festgelegt werden.  
  
-   Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A>-Eigenschaft eines Bildes überschreibt alle anderen Hintergrundeinstellungen.  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a>Zeichnen eines Kreises mit einem benutzerdefinierten Rahmen  
  
1.  Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  In der **Eigenschaften** Fenster, in der `Size` Eigenschaftensatz, `Height` und `Width` gleichen Werte fest.  
  
3.  Legen Sie bei der Eigenschaft `BorderColor` die gewünschte Farbe fest.  
  
4.  Legen Sie für die `BorderStyle`-Eigenschaft einen anderen Wert als `Solid` fest.  
  
5.  Legen Sie für `BorderWidth` die von Ihnen gewünschte Größe in Pixeln fest.  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a>Zeichnen eines Kreises mit einer einfarbigen Füllung  
  
1.  Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  In der **Eigenschaften** Fenster, in der `Size` Eigenschaftensatz, `Height` und `Width` gleichen Werte fest.  
  
3.  Legen Sie bei der Eigenschaft `BackColor` die gewünschte Farbe fest.  
  
4.  Legen Sie die `BackStyle`-Eigenschaft auf `Opaque` fest.  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a>Zeichnen eines Kreises mit einer gemusterten Füllung  
  
1.  Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  In der **Eigenschaften** Fenster, in der `Size` Eigenschaftensatz, `Height` und `Width` gleichen Werte fest.  
  
3.  Legen Sie für die `BackColor`-Eigenschaft die Farbe fest, die Sie für den Hintergrund verwenden möchten.  
  
4.  Legen Sie die `BackStyle`-Eigenschaft auf `Opaque` fest.  
  
5.  Legen Sie für die `FillColor`-Eigenschaft die Farbe fest, die Sie für das Muster festlegen möchten.  
  
6.  Legen Sie für die `FillStyle`-Eigenschaft einen beliebigen Wert fest, der weder `Transparent` noch `Solid` beträgt.  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a>Zeichnen eines Kreises mit gradueller Füllung  
  
1.  Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  In der **Eigenschaften** Fenster, in der `Size` Eigenschaftensatz, `Height` und `Width` gleichen Werte fest.  
  
3.  Legen Sie für die `FillColor`-Eigenschaft die als Anfangsfarbe gewünschte Farbe fest.  
  
4.  Legen Sie für die `FillGradientColor`-Eigenschaft die als Endfarbe gewünschte Farbe fest.  
  
5.  Legen Sie für die `FillGradientStyle` -Eigenschaft einen Wert fest, der nicht `None` fest.  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a>Zeichnen eines Kreises, der mit einem Bild gefüllt ist  
  
1.  Ziehen Sie die `OvalShape` -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  In der **Eigenschaften** Fenster, in der `Size` Eigenschaftensatz, `Height` und `Width` gleichen Werte fest.  
  
3.  Wählen Sie die `BackgroundImage` -Eigenschaft, und klicken Sie auf die **Auslassungszeichen** Schaltfläche (...).  
  
4.  In der **Ressource auswählen** (Dialogfeld), wählen Sie ein Bild angezeigt. Wenn keine Bildressourcen aufgeführt sind, klicken Sie auf **Import** , um den Speicherort einer Bilddatei zu suchen.  
  
5.  Klicken Sie auf **OK** um das Bild einzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [Einführung in das Line-Steuerelement und das Shape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
