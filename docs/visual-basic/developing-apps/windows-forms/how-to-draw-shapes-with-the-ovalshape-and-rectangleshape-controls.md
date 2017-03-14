---
title: "How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "OvalShape control"
  - "shapes, drawing"
  - "RectangleShape control"
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können das <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Steuerelement nutzen, um Kreise und Ovale auf einem Formular oder Container zu zeichnen, sowohl zur Entwurfszeit als auch zur Laufzeit.  Sie können das <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelement nutzen, um Quadrate, Rechtecke oder Rechtecke mit abgerundeten Ecken auf einem Formular oder Container zu zeichnen.  Sie können dieses Steuerelement nutzen, um sowohl zur Entwurfszeit als auch zur Laufzeit Formen zu zeichnen.  
  
 Sie können die Darstellung einer Form durch Ändern der Breite, Farbe und Format des Rahmens anpassen.  Der Hintergrund einer Form ist standardmäßig transparent; Sie können den Hintergrund zum Anzeigen einer durchgängigen Farbe, eines Musters, eines Farbverlaufs \(Übergang von einer Farbe zu einer anderen\) oder eines Bildes anpassen.  
  
### Zeichnen einer einfachen Form zur Entwurfszeit  
  
1.  Ziehen Sie das Steuerelement <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> oder <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> von der Registerkarte **Visual Basic PowerPacks** \(Informationen zur Installation finden Sie unter [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md) in der **Toolbox**\) in ein Formular oder Containersteuerelement.  
  
2.  Ziehen Sie den Zieh\- und Zuschnittpunkt, um die Form in Position und Größe zu ändern.  
  
     Sie können auch die Größe und Position der Form durch Anpassen von `Size` und `Position` Eigenschaften im Fenster **Eigenschaften** ändern.  
  
     Um ein Rechteck mit abgerundeten Ecken zu erstellen, wählen Sie die `CornerRadius`\-Eigenschaft im Fenster **Eigenschaften** und legen Sie diese auf einen Wert, der größer als 0 ist.  
  
3.  Legen Sie im **Eigenschaften**\-Fenster optional weitere Eigenschaften fest, um die Darstellung der Form zu ändern.  
  
### Zeichnen einer einfachen Form zur Laufzeit  
  
1.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**.  
  
2.  Wählen Sie im Dialogfeld **Verweis hinzufügen Microsoft.VisualBasic.PowerPacks.VS** und klicken Sie dann auf **OK**.  
  
3.  Fügen Sie im **Code\-Editor** eine `Imports` oder eine `using`\-Anweisung am Anfang des Moduls ein:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
4.  Fügen Sie den folgenden Code in ein `Event`\-Verfahren ein:  
  
     [!code-cs[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## Anpassen von Formen  
 Wenn Sie die Standardeinstellungen verwenden, werden die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>\-Steuerelemente mit einem durchgehenden schwarzen Rahmen mit einem Pixel Breite und einem transparenten Hintergrund angezeigt.  Sie können Breite, Stil und Farbe des Rahmens ändern, indem Sie Eigenschaften festlegen.  Zusätzliche Eigenschaften ermöglichen Ihnen, den Hintergrund einer Form zu einer Volltonfarbe, einem Muster, Farbverlauf oder einem Bild zu ändern.  
  
 Bevor Sie den Hintergrund einer Form ändern, sollten Sie wissen, wie einige der Eigenschaften interagieren.  
  
-   Die Einstellung der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>\-Eigenschaft hat nur Auswirkungen, wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.BackStyle> festgelegt ist.  
  
-   Wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> festgelegt ist, setzt <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> außer Kraft.  
  
-   Wenn die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>\-Eigenschaft auf einen Musterwert wie <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> oder <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> festgelegt ist, wird das Muster in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> erscheinen.  Der Hintergrund erscheint in der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, sofern die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.BackStyle> festgelegt ist.  
  
-   Um eine graduelle Füllung anzuzeigen, muss die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> festgelegt werden und die <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A>\-Eigenschaft darf nicht auf <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle> festgelegt werden.  
  
-   Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A>\-Eigenschaft eines Bildes überschreibt alle anderen Hintergrundeinstellungen.  
  
#### Zeichnen eines Kreises mit einem benutzerdefinierten Rahmen  
  
1.  Ziehen Sie das `OvalShape`\-Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Legen Sie im Fenster **Eigenschaften** bei der Eigenschaft `Size` für `Height` und `Width` die gleichen Werte fest.  
  
3.  Legen Sie bei der Eigenschaft `BorderColor` die gewünschte Farbe fest.  
  
4.  Legen Sie für die `BorderStyle`\-Eigenschaft einen anderen Wert als `Solid` fest.  
  
5.  Legen Sie für `BorderWidth` die von Ihnen gewünschte Größe in Pixeln fest.  
  
#### Zeichnen eines Kreises mit einer einfarbigen Füllung  
  
1.  Ziehen Sie das `OvalShape`\-Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Legen Sie im Fenster **Eigenschaften** bei der Eigenschaft `Size` für `Height` und `Width` die gleichen Werte fest.  
  
3.  Legen Sie bei der Eigenschaft `BackColor` die gewünschte Farbe fest.  
  
4.  Legen Sie die `BackStyle`\-Eigenschaft auf `Opaque` fest.  
  
#### Zeichnen eines Kreises mit einer gemusterten Füllung  
  
1.  Ziehen Sie das `OvalShape`\-Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Legen Sie im Fenster **Eigenschaften** bei der Eigenschaft `Size` für `Height` und `Width` die gleichen Werte fest.  
  
3.  Legen Sie für die `BackColor`\-Eigenschaft die Farbe fest, die Sie für den Hintergrund verwenden möchten.  
  
4.  Legen Sie die `BackStyle`\-Eigenschaft auf `Opaque` fest.  
  
5.  Legen Sie für die `FillColor`\-Eigenschaft die Farbe fest, die Sie für das Muster festlegen möchten.  
  
6.  Legen Sie für die `FillStyle`\-Eigenschaft einen beliebigen Wert fest, der weder `Transparent` noch `Solid` beträgt.  
  
#### Zeichnen eines Kreises mit gradueller Füllung  
  
1.  Ziehen Sie das `OvalShape`\-Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Legen Sie im Fenster **Eigenschaften** bei der Eigenschaft `Size` für `Height` und `Width` die gleichen Werte fest.  
  
3.  Legen Sie für die `FillColor`\-Eigenschaft die als Anfangsfarbe gewünschte Farbe fest.  
  
4.  Legen Sie für die `FillGradientColor`\-Eigenschaft die als Endfarbe gewünschte Farbe fest.  
  
5.  Legen Sie für die `FillGradientStyle` \-Eigenschaft einen Wert fest, der nicht `None` fest.  
  
#### Zeichnen eines Kreises, der mit einem Bild gefüllt ist  
  
1.  Ziehen Sie das `OvalShape`\-Steuerelement aus der Registerkarte **Visual Basic PowerPacks** in die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Legen Sie im Fenster **Eigenschaften** bei der Eigenschaft `Size` für `Height` und `Width` die gleichen Werte fest.  
  
3.  Wählen Sie die Eigenschaft `BackgroundImage` fest und klicken Sie die Schaltfläche **Ellipse** \(...\).  
  
4.  Wählen Sie im Dialogfeld **Ressource auswählen** ein Bild aus, das angezeigt werden soll.  Wenn keine Bildressourcen aufgeführt werden, klicken Sie auf **Importieren**, um den Speicherort einer Bilddatei zu suchen.  
  
5.  Klicken Sie auf **OK**, um das Bild einzufügen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>   
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>   
 [Introduction to the Line and Shape Controls](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)   
 [How to: Draw Lines with the LineShape Control](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)