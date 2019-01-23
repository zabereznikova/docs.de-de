---
title: Zeichendatentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 5ede86cca1bddb15cab6518e17405837bda008f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536892"
---
# <a name="character-data-types-visual-basic"></a>Zeichendatentypen (Visual Basic)
Visual Basic bietet *Zeichendatentypen* für den Umgang mit druckbaren und anzeigbaren Zeichen. Während beide Unicode-Zeichen verarbeiten `Char` ein einzelnes Zeichen enthält, wohingegen `String` eine unbestimmten Anzahl von Zeichen enthält.  
  
 Eine Tabelle mit einer Seite-an-Seite-Vergleich der Visual Basic-Datentypen, finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Char-Datentyp  
 Die `Char` -Datentyp ist ein einzelnes 2-Byte (16-Bit) Unicodezeichen. Wenn eine Variable immer genau ein Zeichen gespeichert werden, deklarieren Sie sie als `Char`. Zum Beispiel:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Jeden möglichen Wert in eine `Char` oder `String` Variable ist ein *Codepunkt*, oder Zeichencode in Unicode-Zeichensatz. Unicode-Zeichen enthalten, die grundlegende ASCII-Zeichensatz, verschiedene andere Buchstaben, Akzente, Währungssymbole, Brüche, diakritische Zeichen und mathematischen und technischen Symbole.  
  
> [!NOTE]
>  Unicode-Zeichensatz reserviert, die die Codepunkte D800 bis DFFF (55296 bis 55551 decimal) für *Ersatzpaare*, müssen zwei 16-Bit-Werte, um einen einzelnen Codepunkt darzustellen. Ein `Char` Variable kann kein Ersatzzeichenpaar enthalten und eine `String` verwendet zwei Positionen für solch ein Paar.  
  
 Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>String-Typ  
 Die `String` -Datentyp ist eine Sequenz von NULL oder mehr Unicode-Zeichen der 2-Byte-(16-Bit). Wenn eine Variable mit eine unbestimmten Anzahl von Zeichen enthalten kann, deklarieren Sie sie als `String`. Zum Beispiel:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Weitere Informationen finden Sie unter [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Siehe auch
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
