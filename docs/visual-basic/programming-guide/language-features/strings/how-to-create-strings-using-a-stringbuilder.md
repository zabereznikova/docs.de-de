---
title: 'Vorgehensweise: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: dec1afdbd3ca6c0ba719a95906de8cf6fc7ba378
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738798"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Vorgehensweise: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic
In diesem Beispiel erstellt eine lange Zeichenfolge aus vielen kleineren Zeichenfolgen, die mit der <xref:System.Text.StringBuilder> Klasse. Die <xref:System.Text.StringBuilder> Klasse ist effizienter als die `&=` Operators für viele Zeichenfolgen verketten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Instanz der <xref:System.Text.StringBuilder> -Klasse fügt 1.000 Zeichenfolgen an diese Instanz an, und gibt anschließend die Zeichenfolgendarstellung.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden der StringBuilder-Klasse](../../../../standard/base-types/stringbuilder.md)
- [&=-Operator](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Erstellen neuer Zeichenfolgen](../../../../standard/base-types/creating-new.md)
- [Bearbeiten von Zeichenfolgen](../../../../standard/base-types/manipulating-strings.md)
