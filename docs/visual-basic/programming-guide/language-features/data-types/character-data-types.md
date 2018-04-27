---
title: Zeichendatentypen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dca9cde0af08c4113ea9a4644efa40a721b4d9b1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="character-data-types-visual-basic"></a>Zeichendatentypen (Visual Basic)
Visual Basic bietet *Zeichendatentypen* für den Umgang mit druckbaren und anzeigbaren Zeichen. Während beide mit Unicode-Zeichen verarbeiten `Char` ein einzelnes Zeichen enthält, wohingegen `String` eine unbegrenzte Anzahl von Zeichen enthält.  
  
 Eine Tabelle, einen Seite-an-Seite-Vergleich der Visual Basic-Datentypen angezeigt, wird, finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Char-Datentyp  
 Die `Char` -Datentyp ist ein einzelnes aus zwei Bytes (16-Bit) Unicode-Zeichen. Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie es als `Char`. Zum Beispiel:  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 Jeder mögliche Wert in einer `Char` oder `String` Variable ist eine *Codepunkt*, oder Zeichencode im Unicode-Zeichensatz. Unicode-Zeichen umfassen den grundlegenden ASCII-Zeichensatz, verschiedene andere Buchstaben, Akzente, Währungssymbole, Brüche, diakritische Zeichen und mathematische und technische Symbole.  
  
> [!NOTE]
>  Reserviert die Codepunkte D800 bis DFFF (55296 über Dezimalstellen 55551) für die Unicode-Zeichensatz *Ersatzpaare*, was erfordern zwei 16-Bit-Werten, die einen einzelnen Codepunkt darstellen. Ein `Char` -Variable kann kein Ersatzzeichenpaar, und ein `String` verwendet zwei Positionen für solch ein Paar.  
  
 Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>String-Typ  
 Die `String` -Datentyp ist eine Sequenz von NULL oder mehr Unicode-Zeichen für 2-Byte-(16-Bit). Wenn eine Variable eine unbestimmten Anzahl von Zeichen enthalten kann, deklarieren Sie es als `String`. Zum Beispiel:  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 Weitere Informationen finden Sie unter [Zeichenfolgendatentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
