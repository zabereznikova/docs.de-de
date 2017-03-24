---
title: Konstanten und Literale Datentypen (Visual Basic) | Microsoft-Dokumentation
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
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
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
ms.openlocfilehash: 22ad31415ab560b7fd0180a6dadd6d2dcd7ec77a
ms.lasthandoff: 03/13/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a>Konstanten und literale Datentypen (Visual Basic)
Ein Literal ist ein Wert, der als selbst und nicht als Wert einer Variablen oder das Ergebnis eines Ausdrucks, z. B. die Zahl 3 oder die Zeichenfolge "Hello" ausgedrückt wird. Eine Konstante ist ein aussagekräftiger Name, der anstelle eines Literals und behält diese denselben Wert in der gesamten Anwendung, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.  
  
 Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie alle Konstanten explizit mit einem Datentyp deklarieren. Im folgenden Beispiel der Datentyp des `MyByte` explizit als Datentyp deklariert `Byte`:  
  
 [!code-vb[VbVbalrConstants&#1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, kann zum Deklarieren von Konstanten ohne Angabe eines Datentyps mit einer `As` Klausel. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Ein numerisches Ganzzahlliteral umgewandelt wird, werden standardmäßig die `Integer` -Datentyp. Der Standarddatentyp für Gleitkommazahlen lautet `Double`, Schlüsselwörter und `True` und `False` geben einen `Boolean` konstant.  
  
## <a name="literals-and-type-coercion"></a>Literale und Typumwandlung  
 In einigen Fällen empfiehlt es sich um ein Literal in einen bestimmten Datentyp zu erzwingen; z. B. beim Zuweisen einer besonders großen Ganzzahlliteralwert einer Variable vom Typ `Decimal`. Im folgende Beispiel erzeugt einen Fehler:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Der Fehler resultiert aus der Darstellung des Literals. Die `Decimal` -Datentyp kann einen Wert dieser Größe enthalten das Literal wird implizit als eine `Long`, welche nicht.  
  
 Sie können coerce-Literal in einen bestimmten Datentyp auf zwei Arten: durch ein Typzeichen an sie angehängt oder durch Platzieren innerhalb der einschließenden Zeichen. Ein Typzeichen oder umschließende Zeichen muss unmittelbar vorangehen und/oder das Literal ohne Leerzeichen oder Zeichen folgen.  
  
 Um des vorherigen Beispiels zu machen, fügen Sie der `D` -Typzeichen das Literal, wodurch es als dargestellt, eine `Decimal`:  
  
 [!code-vb[VbVbalrConstants&#2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 Das folgende Beispiel veranschaulicht die richtige Verwendung von Typzeichen und umschließenden Zeichen:  
  
 [!code-vb[VbVbalrConstants&3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 Die folgende Tabelle zeigt die umschließenden Zeichen und Typzeichen Zeichen in verfügbar [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|Datentyp|Zeichen|Angehängtes Typzeichen|  
|---|---|---|  
|`Boolean`|(keine)|(keine)|  
|`Byte`|(keine)|(keine)|  
|`Char`|"|A|  
|`Date`|#|(keine)|  
|`Decimal`|(keine)|D oder @|  
|`Double`|(keine)|R oder #|  
|`Integer`|(keine)|I oder %|  
|`Long`|(keine)|L oder &|  
|`Short`|(keine)|S|  
|`Single`|(keine)|F oder!|  
|`String`|"|(keine)|  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)   
 [Gewusst wie: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Option Explicit-Anweisung](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
