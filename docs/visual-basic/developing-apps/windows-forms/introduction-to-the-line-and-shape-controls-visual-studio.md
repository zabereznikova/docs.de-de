---
title: Einführung in das Line-Steuerelement und das Shape-Steuerelement (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3623c2363f39150fd4bb202ba61ebd51df383ca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699921"
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Einführung in das Line-Steuerelement und das Shape-Steuerelement (Visual Studio)
Die Visual Basic Power Packs Line- und Shape-Steuerelemente sind ein Satz von drei grafischen Steuerelementen, die Sie zum Zeichnen von Linien und Formen in Formularen und Containern zu ermöglichen. Die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Steuerelement wird verwendet, um horizontale, vertikale und diagonale Linien zu zeichnen. Die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Steuerelement wird zum Zeichnen der Kreise und Ovale, und die <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelement zum Zeichnen von Rechtecken und Quadraten verwendet wird.  
  
## <a name="line-and-shape-controls"></a>Das Line-Steuerelement und das Shape-Steuerelement  
 Linien-und Formensteuerelemente kapseln viele der Grafikmethoden ein, die in befinden die <xref:System.Drawing> Namespace. Dies ermöglicht Ihnen, Linien und Formen in einem einzigen Schritt zu zeichnen, ohne Grafikobjekte, Stifte und Pinsel erstellen zu müssen. Komplexe Grafiktechniken wie graduelle Füllungen können erreicht werden, indem Sie einige Eigenschaften festlegen.  
  
 Obwohl es auch möglich, Linien und Formen zu zeichnen, mithilfe der Grafikmethoden ist, gibt es mehrere Vorteile, die zum Verwenden der Line- und Shape-Steuerelemente:  
  
-   Grafikmethoden können nur zur Laufzeit aufgerufen werden. Linien-und Formensteuerelemente können zu einem Formular zur Entwurfszeit hinzugefügt werden. Dadurch können Sie sehen, wie sie dargestellt und sie genau positionieren; Sie können auch zur Laufzeit hinzugefügt werden.  
  
-   Linien-und Formensteuerelemente können ausgewählt werden zur Laufzeit, das Ereignisse bereitstellt wie z. B. <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> und <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. Die Ausgaben der Grafikmethoden können nicht ausgewählt werden und keine Ereignisse.  
  
-   Geben Sie die Linien-und Formensteuerelemente <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> und <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> Methoden, mit denen Sie die Z-Reihenfolge zur Entwurfszeit und zur Laufzeit steuern können. Die Z-Reihenfolge von Grafikmethoden kann gesteuert werden, nur durch die Reihenfolge der Ausführung zur Laufzeit ändern.  
  
-   Linien-und Formensteuerelemente sind Fensterlose Steuerelemente. Sie haben keine Fensterhandles und daher weniger Systemressourcen verwenden.  
  
### <a name="object-model"></a>Objektmodell  
 Linien-und Formsteuerelemente von einer Basisklasse ableiten <xref:Microsoft.VisualBasic.PowerPacks.Shape> Klasse, die die freigegebene Eigenschaften, Methoden und Ereignisse definiert.  
  
 Die folgende Abbildung zeigt die Line- und Shape-Objekthierarchie.  
  
 ![Ein Diagramm der Line- und Shape-Objekthierarchie](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line- und Shape-Objekthierarchie  
  
 Die abgeleitete <xref:Microsoft.VisualBasic.PowerPacks.LineShape> -Klasse enthält Eigenschaften, Methoden und Ereignisse, die Zeilen eindeutig sind. Die abgeleitete <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> -Klasse ist die Basisklasse für <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; er enthält Eigenschaften, Methoden und Ereignisse, die für alle Formen. Sie können auch Ableiten aus <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> Erstellen eigener `Shape` Steuerelemente.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Klassen zum Zeichnen der Kreise, Ellipsen, Rechtecken und Rechtecke mit abgerundeten Ecken verwendet werden können.  
  
 Wenn ein Line- oder Shape-Steuerelement hinzugefügt wird, ein Formular oder Container, wie ein unsichtbares <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> Objekt erstellt wird. Die <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> , wobei jede fungiert als eine Leinwand für die Formen innerhalb jedes Containersteuerelement <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> verfügt über eine entsprechende <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> , mit der Sie zum iterieren durch die Line- und Shape-Steuerelemente. Sie können Formen aus einem Container in einen anderen mithilfe von Ausschneiden und einfügen oder per Drag & Drop verschieben. Beim Entfernen des letzten Form aus einem Container, der <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> wird ebenfalls entfernt.  
  
> [!NOTE]
>  Nicht alle Containersteuerelemente unterstützen die Line- und Shape-Steuerelemente. Sie können kein Line- oder Shape-Steuerelement hosten, auf eine <xref:System.Windows.Forms.TableLayoutPanel> oder <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks>
- [Vorgehensweise: Zeichnen von Linien mit dem LineShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [Vorgehensweise: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [Vorgehensweise: Aktivieren Sie die TAB-Taste zwischen Formen](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
