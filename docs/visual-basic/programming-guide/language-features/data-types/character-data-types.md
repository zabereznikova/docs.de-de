---
title: Zeichendatentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7ce600fe188c94593e4c07e37883ca11f90d9ae5
ms.lasthandoff: 03/13/2017

---
# <a name="character-data-types-visual-basic"></a>Zeichendatentypen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet *Zeichendatentypen* für den Umgang mit druckbaren und anzeigbaren Zeichen. Während beide mit Unicode-Zeichen Umgang, `Char` ein einzelnes Zeichen enthält, wohingegen `String` eine unbestimmte Anzahl von Zeichen enthält.  
  
 Für eine Tabelle mit einer Side-by-Side-Vergleich der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen finden Sie in [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Char-Datentyp  
 Die `Char` -Datentyp ist ein einzelnes&2; Bytes (16-Bit) Unicode-Zeichen. Wenn eine Variable immer genau ein Zeichen speichert, deklarieren Sie es als `Char`. Zum Beispiel:  
  
 [!code-vb[VbVbalrCharTypes&#1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 Jeder mögliche Wert einer `Char` oder `String` Variable ist ein *Codepunkt*, Zeichencode im Unicode-Zeichensatz. Unicode-Zeichensatz umfasst den grundlegenden ASCII-Zeichensatz, verschiedene andere Buchstaben, Akzente, Währungssymbole, Bruchzahlen, diakritische Zeichen und mathematische und technische Symbole.  
  
> [!NOTE]
>  Reserviert die Codepunkte D800 bis DFFF (55296 bis 55551 in Dezimalschreibweise) für den Unicode-Zeichensatz *Ersatzpaare*, die zwei 16-Bit-Werte, um eine Codepunkts erfordern. Ein `Char` -Variable kann kein Ersatzzeichenpaar und ein `String` verwendet zwei Positionen für solch ein Paar.  
  
 Weitere Informationen finden Sie unter [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>String-Typ  
 Die `String` -Datentyp ist eine Folge von NULL oder mehr&2; Bytes (16-Bit) Unicode-Zeichen. Wenn eine Variable eine unbestimmte Anzahl von Zeichen enthalten kann, deklarieren Sie es als `String`. Zum Beispiel:  
  
 [!code-vb[VbVbalrCharTypes&#2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 Weitere Informationen finden Sie unter [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
