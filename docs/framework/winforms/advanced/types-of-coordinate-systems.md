---
title: Typen von Koordinatensystemen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 24079f24bdae5fefd785a20dda9b29a190fb4068
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505259"
---
# <a name="types-of-coordinate-systems"></a>Typen von Koordinatensystemen
GDI + verwendet drei Koordinatensysteme: Welt, Seiten- und Gerät. Globale Koordinaten sind die Koordinaten, die zum Modellieren einer bestimmten grafikumgebung verwendet und die Koordinaten, die Sie Methoden in .NET Framework übergeben. Seitenkoordinaten beziehen sich auf das Koordinatensystem, die von einer Zeichenoberfläche, z. B. eines Formulars oder Steuerelements verwendet. Gerätekoordinaten beziehen, die von der physischen Zeichengerät, z. B. einen Bildschirm oder Blatt Papier verwendet. Wenn Sie den Aufruf vornehmen `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, die Punkte, die Sie übergeben die <xref:System.Drawing.Graphics.DrawLine%2A> Methode –`(0, 0)` und `(160, 80)`– werden in der Welt Koordinatenraum. Bevor GDI + die Zeile auf dem Bildschirm zeichnen können, durchlaufen eine Sequenz von Transformationen die Koordinaten. Eine Transformation, wird aufgerufen, die globale Transformation, globale Koordinaten in Seitenkoordinaten konvertiert und eine andere Transformation, die genannte Seitentransformation, Seitenkoordinaten in Gerätekoordinaten.  
  
## <a name="transforms-and-coordinate-systems"></a>Transformationen und Koordinatensysteme  
 Nehmen wir an, dass Sie mit einem Koordinatensystem arbeiten möchten, die dessen Ursprung im Text der Clientbereich statt in der oberen linken Ecke. Angenommen Sie, z. B., dass den Ursprung 100 Pixel vom linken Rand des Clientbereichs und 50 Pixel vom oberen Rand des Clientbereichs sein soll. Die folgende Abbildung zeigt eine solche einem Koordinatensystem.  
  
 ![Koordinatensystem](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Wenn Sie den Aufruf vornehmen `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, erhalten Sie die Zeile, die in der folgenden Abbildung dargestellt.  
  
 ![Koordinatensystem](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Die Koordinaten der Endpunkte der Linie in den drei Koordinatensysteme lauten wie folgt aus:  
  
|||  
|-|-|  
|World|(0, 0), ("160", "80")|  
|Seite|(100, 50), ("260", "130")|  
|Gerät|(100, 50), ("260", "130")|  
  
 Beachten Sie, dass die Seite einen Koordinatenbereich hat seinen Ursprung auf der linken oberen Ecke des Clientbereichs. Dies wird immer der Fall sein. Beachten Sie außerdem, da die Maßeinheit Pixel ist, die Gerätekoordinaten die Seitenkoordinaten identisch sind. Wenn Sie die Maßeinheit mit etwas anderem als Pixel (z. B. Zoll) festlegen, werden die Gerätekoordinaten von den Seitenkoordinaten unterscheiden.  
  
 Die globale Transformation, die globale Koordinaten in Seitenkoordinaten zugeordnet wird, wird, verbleibt in der <xref:System.Drawing.Graphics.Transform%2A> Eigenschaft der <xref:System.Drawing.Graphics> Klasse. Im vorherigen Beispiel ist die globale Transformation ein Übersetzungseinheiten 100 in X-Richtung und 50 Einheiten in der y-Richtung. Im folgenden Beispiel wird die globale Transformation für einen <xref:System.Drawing.Graphics> Objekt aus, und klicken Sie dann verwendet, die <xref:System.Drawing.Graphics> Objekt zum Zeichnen der Linie, die in der obigen Abbildung gezeigt:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 Die Seitentransformation wird Seitenkoordinaten Gerätekoordinaten zugeordnet. Die <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.PageUnit%2A> und <xref:System.Drawing.Graphics.PageScale%2A> Eigenschaften für das Bearbeiten der Seitentransformation. Die <xref:System.Drawing.Graphics> Klasse bietet auch zwei schreibgeschützte Eigenschaften, <xref:System.Drawing.Graphics.DpiX%2A> und <xref:System.Drawing.Graphics.DpiY%2A>, überprüfen Sie die horizontale und vertikale DPI-Wert des Anzeigegeräts.  
  
 Können Sie die <xref:System.Drawing.Graphics.PageUnit%2A> Eigenschaft der <xref:System.Drawing.Graphics> Klasse, einer Maßeinheit als das Pixel an.  
  
> [!NOTE]
>  Kann nicht festgelegt werden die <xref:System.Drawing.Graphics.PageUnit%2A> Eigenschaft <xref:System.Drawing.GraphicsUnit.World>, wie dies keine physische Einheit ist, und wird eine Ausnahme ausgelöst.  
  
 Das folgende Beispiel zeichnet eine Linie von (0, 0), (2, 1), in dem der Punkt ("2", "1") ist 2 Zoll rechts und 1 Zoll nach unten, an dem Punkt (0, 0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Wenn Sie beim Erstellen des Stifts eine Breite nicht angeben, wird im vorherige Beispiel eine Linie gezeichnet, die einen Zoll breit ist. Sie können die Stiftbreite angeben, in das zweite Argument für die <xref:System.Drawing.Pen> Konstruktor:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Wenn Sie davon ausgehen, dass das Anzeigegerät, 96 DPI-Wert in horizontaler Richtung und 96 DPI-Wert in vertikaler Richtung hat, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in der drei Koordinatensysteme:  
  
|||  
|-|-|  
|World|(0, 0), (2, 1)|  
|Seite|(0, 0), (2, 1)|  
|Gerät|(0, 0 (null), (192, 96)|  
  
 Beachten Sie, da der Ursprung der globalen Koordinatensystem auf der linken oberen Ecke des Clientbereichs ist, die Seitenkoordinaten identisch mit der globalen Koordinaten.  
  
 Sie können die Welt und Seite-Transformationen, um eine Reihe von Effekten erzielen kombinieren. Nehmen wir beispielsweise an Zoll als Maßeinheit verwendet werden sollen, und den Ursprung des Koordinatensystems 2 Zoll vom linken Rand des Clientbereichs und 1/2 Zoll zwischen dem oberen Rand des Clientbereichs sein sollen. Im folgenden Beispiel wird die Seite "und" World Transformationen von einem <xref:System.Drawing.Graphics> Objekt aus, und klicken Sie dann zeichnet eine Linie von (0, 0), (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 Die folgende Abbildung zeigt die Zeile und der Koordinatensystem.  
  
 ![Koordinatensystem](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Wenn Sie davon ausgehen, dass das Anzeigegerät, 96 DPI-Wert in horizontaler Richtung und 96 DPI-Wert in vertikaler Richtung hat, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in der drei Koordinatensysteme:  
  
|||  
|-|-|  
|World|(0, 0), (2, 1)|  
|Seite|(2, 0,5), (4, 1.5)|  
|Gerät|(192, 48), (384, 144)|  
  
## <a name="see-also"></a>Siehe auch

- [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md)
- [Matrixdarstellung von Transformationen](matrix-representation-of-transformations.md)
