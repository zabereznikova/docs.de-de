---
title: Einschränken der Zeichenfläche in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672625"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Einschränken der Zeichenfläche in GDI+
Clipping wird Zeichnung auf ein bestimmtes Rechteck oder Region beschränkt. Die folgende Abbildung zeigt die Zeichenfolge "Hello" in einer Region Kern gestalteten abgeschnitten.  
  
 ![Eingeschränkte Zeichnungsoberfläche](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Clipping mit Bereichen  
 Regionen können erstellt werden, aus Pfaden und Pfade können die Umrisse von Zeichenfolgen enthalten, sodass Sie Text mit Kontur für das Clipping verwenden können. Die folgende Abbildung zeigt eine Reihe von konzentrischen Ellipsen, die auf das Innere einer Textzeichenfolge abgeschnitten.  
  
 ![Eingeschränkte Zeichnungsoberfläche](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Um mit Clipping zu zeichnen, erstellen eine <xref:System.Drawing.Graphics> -Objekts seine <xref:System.Drawing.Graphics.Clip%2A> -Eigenschaft, und rufen Sie dann den Zeichenmethoden der, die gleichen <xref:System.Drawing.Graphics> Objekt:  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Verwenden von Bereichen](using-regions.md)
