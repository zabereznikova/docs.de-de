---
title: 'Vorgehensweise: Abflachen eines Kurvenpfads zu einer Linie'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: aa47a655417cdf82d79fb222dc6ff6f6d8c3a947
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601817"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Vorgehensweise: Abflachen eines Kurvenpfads zu einer Linie
Ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert eine Sequenz von Zeilen und Béziersplinekurven. Sie können mehrere Typen von Kurven (Ellipsen, Bögen kardinale Splinekurven) in einen Pfad hinzufügen, aber jede Kurve wird in eine Béziersplinekurve konvertiert, bevor er im Pfad gespeichert wird. Reduzieren einen Pfad besteht aus einzelnen Béziersplinekurve im Pfad in eine Sequenz von geraden Linien konvertieren. Die folgende Abbildung zeigt einen Pfad an, vor und nach der Vereinfachung.  
  
 ![Gerade Linien und Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>So vereinfachen Sie einen Pfad  
  
-   Rufen Sie die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Methode eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> -Methode empfängt ein Flachheitsargument, das den maximalen Abstand zwischen den abgeflachten Pfad und den ursprünglichen Pfad angibt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
