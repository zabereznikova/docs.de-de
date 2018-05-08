---
title: Verwenden der globalen Transformation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: 6a029e17096222d7ed80dea16f91b83a813039f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-world-transformation"></a>Verwenden der globalen Transformation
Die globale Transformation ist eine Eigenschaft der <xref:System.Drawing.Graphics> Klasse. Die Zahlen, die die globale Transformation angeben befinden sich einem <xref:System.Drawing.Drawing2D.Matrix> Objekt, das eine 3 x 3-Matrix darstellt. Die <xref:System.Drawing.Drawing2D.Matrix> und <xref:System.Drawing.Graphics> Klassen verfügen über mehrere Methoden zum Festlegen der Zahlen in die globale Transformationsmatrix.  
  
## <a name="different-types-of-transformations"></a>Verschiedene Arten von Transformationen  
 Im folgenden Beispiel wird der Code zuerst erstellt ein Rechteck, 50 x 50, und sucht er am ursprünglichen Speicherort (0, 0). Der Ursprung befindet sich in der oberen linken Ecke des Clientbereichs.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 Der folgende Code wendet eine Skalierungstransformation, die das Rechteck mit dem Faktor 1,75 entlang der x-Achse an erweitert und verkleinert das Rechteck mit einem Faktor von 0,5 entlang der y-Achse an:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Das Ergebnis ist ein Rechteck, das länger in X-Richtung und in der y-Richtung kürzer ist als die ursprüngliche ist.  
  
 Um das Rechteck statt Skalierung zu wechseln, verwenden Sie den folgenden Code ein:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Um das Rechteck zu übersetzen, verwenden Sie den folgenden Code:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Verwenden von Transformationen in Managed GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
