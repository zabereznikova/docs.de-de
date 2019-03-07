---
title: Bedeutung der Transformationsreihenfolge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order significance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 9fd0764e3e3754fbbaa16441737e0463db3f99a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503176"
---
# <a name="why-transformation-order-is-significant"></a>Bedeutung der Transformationsreihenfolge

Ein einzelnes <xref:System.Drawing.Drawing2D.Matrix> Objekt kann eine einzelne Transformation oder eine Sequenz von Transformationen zu speichern. Letzteres ist eine zusammengesetzte Transformation aufgerufen. Die Matrix eine zusammengesetzte Transformation wird durch Multiplikation der Matrizen der einzelnen Transformationen abgerufen.

## <a name="composite-transform-examples"></a>Beispiele für zusammengesetzte Transformationen

In eine zusammengesetzte Transformation ist die Reihenfolge der einzelnen Transformationen wichtig. Z. B. Wenn Sie zuerst zu drehen, skalieren und dann zu übersetzen, erhalten Sie ein anderes Ergebnis als wenn Sie zuerst übersetzen, drehen und anschließend skalieren. In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], zusammengesetzte Transformationen werden von links nach rechts erstellt. Wenn S, R und T Skalierung, Drehung und Übersetzung-Matrizen sind, klicken Sie dann das Produkt SRT (in dieser Reihenfolge) wird die Matrix der zusammengesetzten Transformation mit ersten Skalierung, klicken Sie dann dreht, und übersetzt. Die Matrix, die das Produkt unterscheidet SRT der Matrix, die das Produkt TRS.

Ein Grund, die Reihenfolge von Bedeutung ist besteht darin, dass Transformationen wie Drehung und Skalierung in Bezug auf den Ursprung des Koordinatensystems sind. Die Skalierung eines Objekts, das am ursprünglichen Speicherort zentriert ist, ergibt ein anderes Ergebnis als die Skalierung eines Objekts, das vom Ursprung weg verschoben wurde. Ebenso erstellt das Drehen eines Objekts, das am ursprünglichen Speicherort zentriert ist ein anderes Ergebnis als Drehen eines Objekts, das vom Ursprung weg verschoben wurde.

Das folgende Beispiel kombiniert die Skalierung, Drehung und Übersetzung (in dieser Reihenfolge), um eine zusammengesetzte Transformation. Das Argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> , die an die <xref:System.Drawing.Graphics.RotateTransform%2A> -Methode gibt an, dass die Drehung die Skalierung erfolgt. Ebenso das Argument <xref:System.Drawing.Drawing2D.MatrixOrder.Append> , die an die <xref:System.Drawing.Graphics.TranslateTransform%2A> -Methode gibt an, dass die Übersetzung die Drehung erfolgt. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> und <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> sind Mitglied der <xref:System.Drawing.Drawing2D.MatrixOrder> Enumeration.

[!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
[!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]

Im folgenden Beispiel wird die gleiche Methode ruft wie im vorherigen Beispiel, aber die Reihenfolge der Aufrufe wird umgekehrt. Die sich ergebende Reihenfolge der Vorgänge wird zuerst zu übersetzen, drehen, und klicken Sie dann die Skalierung an, die ein ganz anderes Ergebnis als ersten Skala ergibt, dann Drehen und dann zu übersetzen.

[!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
[!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]

Eine Möglichkeit zum Umkehren der Reihenfolge der einzelnen Transformationen in einer zusammengesetzten Transformation ist, um die Reihenfolge einer Sequenz von Methodenaufrufen umzukehren. Eine zweite Möglichkeit zur Steuerung der Reihenfolge der Vorgänge ist das Argument für die Matrix-Reihenfolge zu ändern. Das folgende Beispiel entspricht dem vorherigen Beispiel, außer dass <xref:System.Drawing.Drawing2D.MatrixOrder.Append> wurde geändert in <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. Die Matrixmultiplikation erfolgt in der Reihenfolge SRT, in denen die Anpassungsmatrizen für Graustufenwerte für die Skalierung von S, R und T sind, zu drehen und Verschiebung entsprechen. Die Reihenfolge der zusammengesetzten Transformation ist das erste skalieren, drehen und dann zu übersetzen.

[!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
[!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]

Das Ergebnis des unmittelbar vorangehenden Beispiel entspricht die als Ergebnis im ersten Beispiel in diesem Thema. Dies ist, da wir sowohl die Reihenfolge der Aufrufe der-Methode und die Reihenfolge der Matrixmultiplikation umgekehrt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Drawing2D.Matrix>
- [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
- [Verwenden von Transformationen in Managed GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
