---
title: Bereiche in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d3805c2d67f5241425ef72d3802aba996d33cfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="regions-in-gdi"></a>Bereiche in GDI+
Ein Bereich ist ein Teil der Anzeigebereich des ein Ausgabegerät an. Regionen können es sich um einfachen (ein einzelnes Rechteck) oder komplexe (eine Kombination aus Polygone und geschlossene Kurven) handeln. Die folgende Abbildung zeigt zwei Bereiche: einen erstellt aus einem Rechteck und die andere erstellt aus einem Pfad.  
  
 ![Regionen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Verwenden von Bereichen  
 Bereiche werden häufig zum Ausschneiden und Treffertests. Clipping wird das Zeichnen auf einen bestimmten Bereich neben dem Anzeigebereich, in der Regel der Teil, der zu aktualisierenden beschränkt. Treffertests beinhaltet die Überprüfung, um festzustellen, ob der Cursor befindet sich in einem bestimmten Bereich des Bildschirms, wenn eine Maustaste gedrückt wird.  
  
 Sie können einen Bereich aus einem Rechteck oder einen Pfad erstellen. Sie können auch komplexe Regionen erstellen, durch die Kombination der vorhandener Regions. Die <xref:System.Drawing.Region> Klasse bietet die folgenden Methoden zum Kombinieren von Bereichen: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, und <xref:System.Drawing.Region.Complement%2A>.  
  
 Die Schnittmenge der beiden Regionen ist der Satz aller Punkte, die zu beiden Bereichen gehören. Die Union ist der Satz aller Punkte, die zu den anderen oder beide Regionen gehören. Das Komplement eines Datenbereichs ist der Satz aller Punkte, die nicht in der Region sind. Die folgende Abbildung zeigt die Schnittmenge und die Union der beiden Regionen in der vorherigen Abbildung dargestellt.  
  
 ![Regionen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 Die <xref:System.Drawing.Region.Xor%2A> -Methode angewendet wird, um ein Paar von Regionen, erzeugt einen Bereich, der alle Punkte enthält, die zu einer Region oder zur anderen jedoch nicht zu beiden gehören. Die <xref:System.Drawing.Region.Exclude%2A> -Methode angewendet wird, um ein Paar von Regionen, erzeugt eine Region, die alle Punkte in der ersten Region enthält, die nicht im zweiten Bereich enthalten sind. Die folgende Abbildung zeigt die Bereiche, die aus dem Anwenden der <xref:System.Drawing.Region.Xor%2A> und <xref:System.Drawing.Region.Exclude%2A> Methoden, um die beiden Bereiche am Anfang dieses Themas.  
  
 ![Regionen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Um einen Bereich zu füllen, müssen Sie eine <xref:System.Drawing.Graphics> -Objekt, eine <xref:System.Drawing.Brush> -Objekt, und ein <xref:System.Drawing.Region> Objekt. Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.FillRegion%2A> -Methode, und die <xref:System.Drawing.Brush> Objekt speichert Attribute für die Füllung, z. B. Farbe oder ein Muster. Das folgende Beispiel füllt einen Bereich mit einer Volltonfarbe aus.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Verwenden von Bereichen](../../../../docs/framework/winforms/advanced/using-regions.md)
