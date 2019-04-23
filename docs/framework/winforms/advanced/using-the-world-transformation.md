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
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139957"
---
# <a name="using-the-world-transformation"></a>Verwenden der globalen Transformation
Die globale Transformation ist eine Eigenschaft der <xref:System.Drawing.Graphics> Klasse. Die Zahlen, die die globale Transformation angeben, befinden sich in einem <xref:System.Drawing.Drawing2D.Matrix> -Objekt, das eine 3 x 3-Matrix darstellt. Die <xref:System.Drawing.Drawing2D.Matrix> und <xref:System.Drawing.Graphics> Klassen verfügen über mehrere Methoden zum Festlegen der Zahlen in die globale Transformationsmatrix.  
  
## <a name="different-types-of-transformations"></a>Verschiedene Arten von Transformationen  
 Im folgenden Beispiel wird der Code zuerst erstellt ein Rechteck 50 x 50, und sucht er am Ursprung (0, 0). Der Ursprung befindet sich in der oberen linken Ecke des Clientbereichs.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 Der folgende Code gilt eine Skalierungstransformation, die erweitert das Rechteck mit einem Faktor von 1,75 in X-Richtung und verkleinert das Rechteck um den Faktor 0,5 in y-Richtung:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Das Ergebnis ist ein Rechteck, mehr in Richtung der x-Achse und die y-Richtung kürzer als das Original.  
  
 Um das Rechteck, anstelle es zu drehen, verwenden Sie den folgenden Code:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Um das Rechteck zu übersetzen, verwenden Sie den folgenden Code:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Drawing2D.Matrix>
- [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md)
- [Verwenden von Transformationen in Managed GDI+](using-transformations-in-managed-gdi.md)
