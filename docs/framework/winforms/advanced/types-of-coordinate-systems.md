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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159805"
---
# <a name="types-of-coordinate-systems"></a>Typen von Koordinatensystemen
GDI+ verwendet drei Koordinaten Bereiche: "World", "page" und "Device". Globale Koordinaten sind die Koordinaten, die verwendet werden, um eine bestimmte Grafik Welt zu modellieren, und sind die Koordinaten, die Sie an Methoden in der .NET Framework übergeben. Seiten Koordinaten verweisen auf das Koordinatensystem, das von einer Zeichen Oberfläche verwendet wird, z. b. ein Formular oder ein Steuerelement. Geräte Koordinaten sind die Koordinaten, die von dem physischen Gerät verwendet werden, auf dem Sie gezeichnet werden, z. b. ein Bildschirm oder ein Papierblatt. Wenn Sie den-Aufruf`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`durchführen, werden die Punkte, die Sie an die <xref:System.Drawing.Graphics.DrawLine%2A>-`(0, 0)` Methode – und `(160, 80)`übergeben, im weltweiten Koordinaten Bereich angezeigt. Bevor GDI+ die Linie auf dem Bildschirm zeichnen kann, durchlaufen die Koordinaten eine Sequenz von Transformationen. Eine Transformation, die als globale Transformation bezeichnet wird, konvertiert globale Koordinaten in Seiten Koordinaten, und eine andere Transformation, die als Seiten Transformation bezeichnet wird, konvertiert Seiten Koordinaten in Geräte Koordinaten.  
  
## <a name="transforms-and-coordinate-systems"></a>Transformationen und Koordinatensysteme  
 Angenommen, Sie möchten mit einem Koordinatensystem arbeiten, dessen Ursprung im Text des Client Bereichs liegt, und nicht in der oberen linken Ecke. Angenommen, Sie möchten, dass der Ursprung 100 Pixel vom linken Rand des Client Bereichs und 50 Pixel vom oberen Rand des Client Bereichs sein soll. Die folgende Abbildung zeigt ein solches Koordinatensystem.  
  
 ![Koordinaten System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Wenn Sie den-`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`abrufen, erhalten Sie die in der folgenden Abbildung gezeigte Zeile.  
  
 ![Koordinaten System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Die Koordinaten der Endpunkte der Zeile in den drei Koordinaten Räumen lauten wie folgt:  
  
|||  
|-|-|  
|Welt|(0,0) bis (160, 80)|  
|Seite|(100, 50) bis (260, 130)|  
|Gerät|(100, 50) bis (260, 130)|  
  
 Beachten Sie, dass der Seiten Koordinaten Bereich seinen Ursprung in der oberen linken Ecke des Client Bereichs hat. Dies ist immer der Fall. Beachten Sie außerdem, dass die Geräte Koordinaten den Seiten Koordinaten entsprechen, da die Maßeinheit das Pixel ist. Wenn Sie die Maßeinheit auf einen anderen Wert als Pixel festlegen (z. b. Zoll), unterscheiden sich die Geräte Koordinaten von den Seiten Koordinaten.  
  
 Die globale Transformation, die globale Koordinaten zu Seiten Koordinaten zuordnet, wird in der <xref:System.Drawing.Graphics.Transform%2A>-Eigenschaft der <xref:System.Drawing.Graphics>-Klasse gespeichert. Im vorherigen Beispiel handelt es sich bei der Welt Transformation um eine Translation 100-Einheiten in der x-Richtung und 50-Einheiten in der y-Richtung. Im folgenden Beispiel wird die globale Transformation eines <xref:System.Drawing.Graphics> Objekts festgelegt, und anschließend wird dieses <xref:System.Drawing.Graphics> Objekt verwendet, um die in der vorherigen Abbildung gezeigte Zeile zu zeichnen:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 Die Seite Transformation ordnet den Geräte Koordinaten Seiten Koordinaten zu. Die <xref:System.Drawing.Graphics>-Klasse stellt die Eigenschaften <xref:System.Drawing.Graphics.PageUnit%2A> und <xref:System.Drawing.Graphics.PageScale%2A> zum Bearbeiten der Seiten Transformation bereit. Die <xref:System.Drawing.Graphics>-Klasse bietet auch zwei schreibgeschützte Eigenschaften, <xref:System.Drawing.Graphics.DpiX%2A> und <xref:System.Drawing.Graphics.DpiY%2A>, um die horizontalen und vertikalen Punkte pro Zoll des Anzeige Geräts zu untersuchen.  
  
 Sie können die <xref:System.Drawing.Graphics.PageUnit%2A>-Eigenschaft der <xref:System.Drawing.Graphics>-Klasse verwenden, um eine andere Maßeinheit als das Pixel anzugeben.  
  
> [!NOTE]
> Die <xref:System.Drawing.Graphics.PageUnit%2A>-Eigenschaft kann nicht auf <xref:System.Drawing.GraphicsUnit.World>festgelegt werden, da es sich nicht um eine physische Einheit handelt, und es wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel wird eine Zeile von (0,0) zu (2, 1) gezeichnet, wobei der Punkt (2, 1) 2 Zoll nach rechts und 1 Zoll vom Punkt (0,0) ist:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> Wenn Sie beim Erstellen des Stifts keine Stift Breite angeben, wird im vorhergehenden Beispiel eine Linie mit einer Breite von einem Zoll gezeichnet. Sie können die Stift Breite im zweiten Argument für den <xref:System.Drawing.Pen>-Konstruktor angeben:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Wenn wir davon ausgehen, dass das Anzeigegerät 96 Punkte pro Zoll in horizontaler Richtung und 96 Punkte pro Zoll in vertikaler Richtung aufweist, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in den drei Koordinaten Räumen:  
  
|||  
|-|-|  
|Welt|(0,0) bis (2, 1)|  
|Seite|(0,0) bis (2, 1)|  
|Gerät|(0,0) bis (192, 96)|  
  
 Beachten Sie Folgendes: da sich der Ursprung des World-Koordinaten Bereichs in der oberen linken Ecke des Client Bereichs befindet, sind die Seiten Koordinaten identisch mit den World-Koordinaten.  
  
 Sie können die Transformationen für Welt und Seite kombinieren, um eine Vielzahl von Effekten zu erzielen. Angenommen, Sie möchten Zoll als Maßeinheit verwenden, und Sie möchten, dass der Ursprung ihres Koordinatensystems 2 Zoll vom linken Rand des Client Bereichs und 1/2 Zoll vom oberen Rand des Client Bereichs ist. Im folgenden Beispiel werden die Welt-und Seiten Transformationen eines <xref:System.Drawing.Graphics> Objekts festgelegt, und anschließend wird eine Linie von (0,0) zu (2, 1) gezeichnet:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 In der folgenden Abbildung ist die Linie und das Koordinatensystem dargestellt.  
  
 ![Koordinaten System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Wenn wir davon ausgehen, dass das Anzeigegerät 96 Punkte pro Zoll in horizontaler Richtung und 96 Punkte pro Zoll in vertikaler Richtung aufweist, haben die Endpunkte der Linie im vorherigen Beispiel die folgenden Koordinaten in den drei Koordinaten Räumen:  
  
|||  
|-|-|  
|Welt|(0,0) bis (2, 1)|  
|Seite|(2, 0,5) bis (4, 1,5)|  
|Gerät|(192, 48) bis (384, 144)|  
  
## <a name="see-also"></a>Siehe auch

- [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md)
- [Matrixdarstellung von Transformationen](matrix-representation-of-transformations.md)
