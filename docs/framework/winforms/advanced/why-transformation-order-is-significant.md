---
title: Bedeutung der Transformationsreihenfolge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 943bfa73b54a1ac5d68d21d2bb6e271133db595a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526076"
---
# <a name="why-transformation-order-is-significant"></a>Bedeutung der Transformationsreihenfolge
Ein einzelnes <xref:System.Drawing.Drawing2D.Matrix> Objekt kann eine einzelne Transformation oder eine Sequenz von Transformationen zu speichern. Der zweite Wert ist eine zusammengesetzte Transformation aufgerufen. Die Matrix eine zusammengesetzte Transformation wird durch Multiplikation der Matrizen der einzelnen Transformationen abgerufen.  
  
## <a name="composite-transform-examples"></a>Beispiele für zusammengesetzte Transformationen  
 In eine zusammengesetzte Transformation ist die Reihenfolge der einzelnen Transformationen wichtig. Z. B. Wenn Sie zuerst drehen, und klicken Sie dann zu skalieren, übersetzen, erhalten Sie ein anderes Ergebnis als wenn Sie zuerst zu übersetzen, drehen und anschließend zu skalieren. In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], zusammengesetzte Transformationen werden von links nach rechts erstellt. Wenn S und R, T Skalierung, Drehung und Übersetzung Matrizen sind, klicken Sie dann das Produkt SRT (in dieser Reihenfolge) wird die Matrix der zusammengesetzte Transformation dieser ersten Skalen, klicken Sie dann dreht und übersetzt. Die Matrix, die das Produkt unterscheidet sich SRT aus der Matrix mit dem Produkt TRS erzeugt.  
  
 Reihenfolge von Bedeutung ist ein Grund besteht darin, dass Transformationen wie Drehung und Skalierung in Bezug auf den Ursprung des Koordinatensystems sind. Ein Objekt, das am ursprünglichen Speicherort zentriert ist die Skalierung, ergibt ein anderes Ergebnis als die Skalierung eines Objekts, das vom Ursprung verschoben wurde. Drehen eines Objekts ist, der sich am ursprünglichen Speicherort erzeugt auf ähnliche Weise ein anderes Ergebnis als Drehen eines Objekts, das vom Ursprung verschoben wurde.  
  
 Das folgende Beispiel kombiniert die Skalierung, Drehung und Verschiebung (in dieser Reihenfolge), um eine zusammengesetzte Transformation. Das Argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> übergeben, um die <xref:System.Drawing.Graphics.RotateTransform%2A> Methode gibt an, dass die Drehung der Skalierung folgen. Entsprechend dem Argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> übergeben, um die <xref:System.Drawing.Graphics.TranslateTransform%2A> Methode gibt an, dass die Übersetzung die Rotation folgen. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> und <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> sind Mitglied der <xref:System.Drawing.Drawing2D.MatrixOrder> Enumeration.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 Im folgenden Beispiel wird die gleiche Methodenaufrufe wie im vorangehenden Beispiel, aber die Reihenfolge der Aufrufe wird umgekehrt. Die sich ergebende Reihenfolge der Vorgänge wird zuerst zu übersetzen, drehen, Skalierung, das ein sehr unterschiedliche Ergebnis als ersten Skala ergibt, dann zu rotieren, und dann zu übersetzen.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Eine Möglichkeit, die Reihenfolge der einzelnen Transformationen in einer zusammengesetzten Transformation umzukehren, wird um die Reihenfolge einer Sequenz von Methodenaufrufen umzukehren. Eine zweite Möglichkeit zur Steuerung der Reihenfolge der Vorgänge ist so ändern Sie die Matrix Order-Argument. Im folgende Beispiel entspricht dem vorherigen Beispiel, außer dass <xref:System.Drawing.Drawing2D.MatrixOrder.Append> wurde geändert in <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. Die Matrixmultiplikation erfolgt in der Reihenfolge SRT, S und R, T die Matrizen für Skalierung gegangenem, zu drehen und bzw. zu übersetzen. Die Reihenfolge der zusammengesetzten Transformation ist der ersten Skala drehen, und dann zu übersetzen.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Das Ergebnis des unmittelbar vorangehenden Beispiel entspricht dem als Ergebnis der im ersten Beispiel in diesem Thema. Dies ist, da wir die Reihenfolge der Aufrufe der-Methode und die Reihenfolge der Matrixmultiplikation umgekehrt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Verwenden von Transformationen in Managed GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
