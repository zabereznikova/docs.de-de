---
title: Zeichendatentypen
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 5fde5eff40d83bdd7d90cd611bd6749106db6e16
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077175"
---
# <a name="character-data-types-visual-basic"></a>Zeichendatentypen (Visual Basic)

Visual Basic stellt *Zeichen Datentypen* für das Behandeln von druckbaren und darstellbaren Zeichen bereit. Obwohl beide Unicode-Zeichen `Char` enthalten, enthält ein einzelnes Zeichen, wohingegen `String` eine unbegrenzte Anzahl von Zeichen enthält.  
  
 Eine Tabelle, in der ein paralleler Vergleich der Visual Basic-Datentypen angezeigt wird, finden Sie unter [Datentypen](../../../language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Char-Typ  

 Der- `Char` Datentyp ist ein einzelnes 2-Byte-Unicode-Zeichen (16 Bit). Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie Sie als `Char` . Beispiel:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Jeder mögliche Wert in einer- `Char` oder- `String` Variablen ist ein *Codepunkt*oder Zeichencode im Unicode-Zeichensatz. Unicode-Zeichen umfassen den grundlegenden ASCII-Zeichensatz, verschiedene andere alphabetische Buchstaben, Akzente, Währungssymbole, Bruchzeichen, Diakritik und mathematische und technische Symbole.  
  
> [!NOTE]
> Der Unicode-Zeichensatz reserviert die Code Punkte D800 und durch DFFF (55296 bis 55551 Decimal) für *Ersatz Zeichenpaare*, bei denen 2 16-Bit-Werte erforderlich sind, um einen einzelnen Codepunkt darzustellen. Eine `Char` Variable kann kein Ersatz Zeichenpaar enthalten, und eine `String` verwendet zwei Positionen, um ein solches Paar zu speichern.  
  
 Weitere Informationen finden Sie unter [Char-Datentyp](../../../language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Zeichenfolgentyp  

 Der- `String` Datentyp ist eine Sequenz von NULL oder mehr 2-Byte-Unicode-Zeichen (16 Bit). Wenn eine Variable eine unbestimmte Anzahl von Zeichen enthalten kann, deklarieren Sie Sie als `String` . Beispiel:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Weitere Informationen finden Sie unter [String Data Type](../../../language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Siehe auch

- [Elementare Datentypen](elementary-data-types.md)
- [Zusammengesetzte Datentypen](composite-data-types.md)
- [Generische Typen in Visual Basic (Visual Basic)](generic-types.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Typzeichen](type-characters.md)
