---
title: "Introduction to the Line and Shape Controls (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line control, overview"
  - "Shape control, overview"
  - "lines, drawing"
  - "shapes, drawing"
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Introduction to the Line and Shape Controls (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Das Line\- und das Shape\-Steuerelement von Visual Basic Power Packs bestehen aus drei grafischen Steuerelementen, mit denen Sie Linien und Formen auf Formularen und in Containern zeichnen können.  Das <xref:Microsoft.VisualBasic.PowerPacks.LineShape>\-Steuerelement wird verwendet, um horizontale, vertikale, und diagonale Linien zu zeichnen.  Das <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>\-Steuerelement dient zum Zeichnen von Kreisen und Ovalen und das <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>\-Steuerelement zum Zeichnen von Rechtecken und Quadraten.  
  
## Line\-Steuerelement und Shape\-Steuerelement  
 Das Line\- und das Shape\-Steuerelement vereinen mehrere Grafikmethoden, die im <xref:System.Drawing>\-Namespace enthalten sind.  Auf diese Weise können Sie in nur einem Schritt Linien und Formen zeichnen, ohne Grafikobjekte, Stifte und Pinsel erstellen zu müssen.  Komplexe Grafiktechniken, wie z. B. Farbverläufe, können mit einigen wenigen Eigenschafteneinstellungen realisiert werden.  
  
 Linien und Formen können zwar auch mit Grafikmethoden gezeichnet werden, das Line\- und das Shape\-Steuerelement bieten jedoch zahlreiche Vorteile:  
  
-   Grafikmethoden können nur zur Laufzeit aufgerufen werden.  Das Line\- und das Shape\-Steuerelement können einem Formular hingegen zur Entwurfszeit hinzugefügt werden.  Hierdurch können Sie das Erscheinungsbild und die Position exakt überprüfen. Die Steuerelemente können aber auch zur Laufzeit hinzugefügt werden.  
  
-   Das Line\- und das Shape\-Steuerelement können zur Laufzeit ausgewählt werden und stellen Ereignisse wie <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> und <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A> bereit.  Die Ausgaben von Grafikmethoden können nicht ausgewählt werden und stellen keine Ereignisse bereit.  
  
-   Das Line\- und das Shape\-Steuerelement stellen <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A>\- und <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A>\-Methoden bereit, mit deren Hilfe Sie die Z\-Reihenfolge zur Entwurfszeit und zur Laufzeit steuern können.  Die Z\-Reihenfolge von Grafikmethoden kann nur gesteuert werden, indem die Ausführungsreihenfolge zur Laufzeit geändert wird.  
  
-   Durch das Line\- und das Shape\-Steuerelement werden keine Fenster aufgerufen. Dadurch, dass sie keine Fensterhandles aufweisen, werden weniger Systemressourcen beansprucht.  
  
### Objektmodell  
 Das Line\- und das Shape\-Steuerelement werden aus einer <xref:Microsoft.VisualBasic.PowerPacks.Shape>\-Basisklasse abgeleitet, durch die die gemeinsamen Eigenschaften, Methoden und Ereignisse definiert werden.  
  
 In der folgenden Abbildung werden die Line\- und Shape\-Objekthierarchie dargestellt.  
  
 ![Ein Diagramm der Line&#45; und Shape&#45;Objekthierarchie](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line\- und Shape\-Objekthierarchie  
  
 Die abgeleitete <xref:Microsoft.VisualBasic.PowerPacks.LineShape>\-Klasse enthält Eigenschaften, Methoden und Ereignisse für Linien.  Die abgeleitete <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>\-Klasse ist die Basisklasse für <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>. Sie enthält Eigenschaften, Methoden und Ereignisse, die für alle Formen gleich sind.  Sie können für die Ableitung auch <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> verwenden, um eigene `Shape`\-Steuerelemente zu erstellen.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>\- und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>\-Klasse dienen zum Zeichnen von Kreisen, Ovalen, Rechtecken und Rechtecken mit abgerundeten Ecken.  
  
 Wenn Sie einem Formular oder einem Container ein Line\- oder Shape\-Steuerelement hinzufügen, wird ein unsichtbares <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>\-Objekt erstellt.  Dabei fungiert <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> als eine Leinwand für die Formen in den einzelnen Containersteuerelementen. Jeder <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> verfügt über eine entsprechende <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection>, sodass Sie die Line\- und Shape\-Steuerelemente durchlaufen können.  Sie können Formen von einem Container in einen anderen verschieben, indem Sie diese ausschneiden und einfügen oder indem Sie sie ziehen und ablegen.  Wenn die letzte Form aus einem Container entfernt wurde, wird der <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> ebenfalls entfernt.  
  
> [!NOTE]
>  Nicht alle Containersteuerelemente unterstützen das Line\- und das Shape\-Steuerelement.  <xref:System.Windows.Forms.TableLayoutPanel> oder <xref:System.Windows.Forms.FlowLayoutPanel> können beispielsweise nicht als Host für ein Line\- oder Shape\-Steuerelement fungieren.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks>   
 [How to: Draw Lines with the LineShape Control](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [How to: Draw Shapes with the OvalShape and RectangleShape Controls](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [How to: Enable Tabbing Between Shapes](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)