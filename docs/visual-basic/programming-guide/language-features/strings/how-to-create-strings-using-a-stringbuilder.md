---
title: 'Vorgehensweise: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834191"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Vorgehensweise: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic
In diesem Beispiel erstellt eine lange Zeichenfolge aus vielen kleineren Zeichenfolgen, die mit der <xref:System.Text.StringBuilder> Klasse. Die <xref:System.Text.StringBuilder> Klasse ist effizienter als die `&=` Operators für viele Zeichenfolgen verketten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Instanz der <xref:System.Text.StringBuilder> -Klasse fügt 1.000 Zeichenfolgen an diese Instanz an, und gibt anschließend die Zeichenfolgendarstellung.  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden der StringBuilder-Klasse](../../../../standard/base-types/stringbuilder.md)
- [&=-Operator](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Erstellen neuer Zeichenfolgen](../../../../standard/base-types/creating-new.md)
- [Bearbeiten von Zeichenfolgen](../../../../standard/base-types/manipulating-strings.md)
