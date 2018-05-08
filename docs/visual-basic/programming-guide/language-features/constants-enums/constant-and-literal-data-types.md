---
title: Konstanten und literale Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Konstanten und literale Datentypen (Visual Basic)
Ein Literal ist ein Wert, der als selbst und nicht als Wert einer Variablen oder das Ergebnis eines Ausdrucks, z. B. die Zahl 3 oder die Zeichenfolge "Hello" ausgedrückt wird. Eine Konstante ist, einen aussagekräftigen Namen, der anstelle eines Literals und behält der gleiche Wert in der gesamten Anwendung, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.  
  
 Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie alle Konstanten explizit mit einem Datentyp deklarieren. Im folgenden Beispiel der Datentyp des `MyByte` wird als Datentyp explizit deklariert `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Sie Deklarieren einer Konstante, ohne dass einen Datentyp mit einer `As` Klausel. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Ein numerisches Ganzzahlliteral umgewandelt wird, werden standardmäßig die `Integer` -Datentyp. Der Standarddatentyp für Gleitkommazahlen ist `Double`, Schlüsselwörter und `True` und `False` Geben Sie einen `Boolean` konstant.  
  
## <a name="literals-and-type-coercion"></a>Literale und Typkoersion  
 In einigen Fällen empfiehlt es sich um ein Literal in einen bestimmten Datentyp erzwingen; beispielsweise, wenn Sie eine Variable des Typs einer besonders großen Ganzzahlliteralwert zuweisen `Decimal`. Im folgende Beispiel wird einen Fehler generiert:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Der Fehler resultiert aus der Darstellung des Literals. Die `Decimal` -Datentyp kann einen Wert enthalten dieser Größe, aber das Literal liegt implizit als eine `Long`, welche nicht.  
  
 Sie können ein Literal in einen bestimmten Datentyp auf zwei Arten coerce: durch Anhängen ein Typzeichen, oder legen Sie das Element innerhalb der einschließenden Zeichen. Ein Typzeichen oder umschließende Zeichen muss unmittelbar vorangestellt und/oder führen Sie das Literal, ohne Leerzeichen oder Zeichen jeglicher Art.  
  
 Um das vorherige Beispiel arbeiten zu machen, können Sie Anfügen der `D` -Typzeichen dem Literal, wodurch es als dargestellt wird ein `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 Das folgende Beispiel veranschaulicht die richtige Verwendung von Typzeichen und umschließenden Zeichen:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 Die folgende Tabelle zeigt die umschließenden Zeichen und Typzeichen, die in Visual Basic verfügbar.  
  
|Datentyp|Einschließen von Zeichen|Angefügte Typzeichen|  
|---|---|---|  
|`Boolean`|(keine)|(keine)|  
|`Byte`|(keine)|(keine)|  
|`Char`|"|C|  
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
 [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
