---
title: 'Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 03138a851afc55f735cc66edeb345817428a0452
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344387"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)
This example creates the string "abcd" from individual characters.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 This method has no special requirements.  
  
 The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string. The null character will be included with the string, but characters following the null character will not be displayed in some situations.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String>
- [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
