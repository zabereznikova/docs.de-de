---
title: 'Vorgehensweise: Erstellen Sie eine Zeichenfolge aus einem Array von Char-Werten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 1f72cb86ffa38dc929062fab2f5592a781f2de27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831825"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Vorgehensweise: Erstellen Sie eine Zeichenfolge aus einem Array von Char-Werten (Visual Basic)
Dieses Beispiel erstellt die Zeichenfolge "Abcd" aus einzelnen Zeichen.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Methode hat keine besonderen Anforderungen.  
  
 Die Syntax `"a"c`, bei dem ein einzelnes `c` basiert auf ein einzelnes Zeichen in Anführungszeichen einschließen, wird verwendet, um ein Zeichenliteral erstellt.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 NULL-Zeichen (Äquivalent zu `Chr(0)`) in der Zeichenfolge nach zu unerwarteten Ergebnissen führen, wenn Sie die Zeichenfolge verwenden. Das Null-Zeichen werden in der Zeichenfolge enthalten, aber das Nullzeichen folgen Zeichen in einigen Fällen nicht angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String>
- [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
