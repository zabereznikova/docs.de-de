---
title: Einführung in das Line-Steuerelement und das Shape-Steuerelement (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3ad740f7dd15194830959a5493970b4ba54ce142
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Einführung in das Line-Steuerelement und das Shape-Steuerelement (Visual Studio)
Die Visual Basic Power Packs Line- und Shape-Steuerelemente sind eine Gruppe von drei grafische Steuerelemente, die Sie zum Zeichnen von Linien und Formen auf Formularen und Containern zu ermöglichen. Die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Steuerelement wird verwendet, um die horizontale, vertikale und diagonale Linien zu zeichnen. Die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Steuerelement wird verwendet, um Kreise und Ovale, zeichnen und die <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelement wird verwendet, um Rechtecke und Quadrate gezeichnet werden soll.  
  
## <a name="line-and-shape-controls"></a>Das Line-Steuerelement und das Shape-Steuerelement  
 Die Linien- und Formsteuerelemente kapseln vielen Grafikmethoden, die in enthaltenen der <xref:System.Drawing> Namespace. Dadurch können Sie Zeichnen von Linien und Formen in einem einzigen Schritt ohne Grafikobjekten, Stifte und Pinsel erstellen zu müssen. Komplexe Grafiktechniken wie Farbverläufe können erreicht werden, indem Sie nur einige Eigenschaften festlegen.  
  
 Obwohl es auch möglich, Linien und Formen zu zeichnen, indem Sie mithilfe von Grafikmethoden ist, stehen verschiedene Vorteile gegenüber der Verwendung der Line- und Shape-Steuerelemente:  
  
-   Grafikmethoden können nur zur Laufzeit aufgerufen werden. Die Linien- und Formsteuerelemente können zu einem Formular zur Entwurfszeit hinzugefügt werden. Dadurch können Sie die Aussehen feststellen, und positionieren Sie sie genau; Sie können auch zur Laufzeit hinzugefügt werden.  
  
-   Linien- und Formsteuerelemente können ausgewählt werden zur Laufzeit, z. B. Bereitstellen von Ereignissen <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> und <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. Die Ausgaben von Grafikmethoden können nicht ausgewählt werden und bieten keine Ereignisse.  
  
-   Geben Sie die Linien- und Formsteuerelemente <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> und <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> Methoden, mit denen Sie ihre Z-Reihenfolge zur Entwurfszeit und zur Laufzeit steuern können. Die Z-Reihenfolge von Grafikmethoden kann gesteuert werden, nur durch ihre Reihenfolge der Ausführung zur Laufzeit ändern.  
  
-   Die Linien- und Formsteuerelemente sind Fensterlose Steuerelemente. Sie haben keine Fensterhandles und daher weniger Systemressourcen verwenden.  
  
### <a name="object-model"></a>Objektmodell  
 Linien- und Formsteuerelemente von einer Basisklasse ableiten <xref:Microsoft.VisualBasic.PowerPacks.Shape> Klasse, die die gemeinsamen Eigenschaften, Methoden und Ereignisse definiert.  
  
 Die folgende Abbildung zeigt die Line- und Shape-Objekthierarchie.  
  
 ![Ein Diagramm der Line- und Shape-Objekthierarchie](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line- und Shape-Objekthierarchie  
  
 Die abgeleitete <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Klasse enthält Eigenschaften, Methoden und Ereignisse, die Zeilen eindeutig sind. Die abgeleitete <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> Klasse ist die Basisklasse für <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; er enthält Eigenschaften, Methoden und Ereignisse, die alle Formen gemeinsam. Sie können auch aus ableiten <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> Erstellen eigener `Shape` Steuerelemente.  
  
 Die <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> und <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Klassen verwendet werden können, um Kreise, Ellipsen, Rechtecke und Rechtecke mit abgerundeten Ecken zu zeichnen.  
  
 Wenn ein Line- oder Shape-Steuerelement hinzugefügt wird, ein Formular oder Container, wie eine unsichtbare <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> Objekt erstellt wird. Die <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> , wobei jede fungiert als ein Zeichenbereich für die Formen innerhalb jedes Containersteuerelement <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> verfügt über ein entsprechendes <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> mit der Sie die Linien- und Formsteuerelemente durchlaufen. Sie können Formen aus einem Container in einen anderen mithilfe von Ausschneiden und einfügen oder per Drag & Drop verschieben. Beim Entfernen des letzten Form aus einem Container, der <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> wird ebenfalls entfernt.  
  
> [!NOTE]
>  Nicht alle Containersteuerelemente unterstützen die Line- und Shape-Steuerelemente. Sie können kein Line- oder Shape-Steuerelement hosten, auf eine <xref:System.Windows.Forms.TableLayoutPanel> oder ein <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks>  
 [Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
