---
title: 'Gewusst wie: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 49f3271d41e9e858c6ecafe1dde5330ebff767f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647731"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Gewusst wie: Erstellen von Zeichenfolgen mit StringBuilder in Visual Basic
In diesem Beispiel erstellt eine lange Zeichenfolge aus vielen kleineren Zeichenfolgen, die mithilfe der <xref:System.Text.StringBuilder> Klasse. Die <xref:System.Text.StringBuilder> Klasse ist effizienter als die `&=` Operator für viele Zeichenfolgen verketten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Instanz von der <xref:System.Text.StringBuilder> -Klasse, fügt Sie 1.000 Zeichenfolgen an diese Instanz und gibt die Zeichenfolgendarstellung.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der StringBuilder-Klasse](../../../../standard/base-types/stringbuilder.md)  
 [&=-Operator](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Erstellen neuer Zeichenfolgen](../../../../standard/base-types/creating-new.md)  
 [Bearbeiten von Zeichenfolgen](../../../../standard/base-types/manipulating-strings.md)  
 [Zeichenfolgen-Beispiel](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))
