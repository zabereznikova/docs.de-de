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
ms.openlocfilehash: d85ff343587e8689a4859a09c8dc80932374a82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498647"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Konstanten und literale Datentypen (Visual Basic)
Ein Literal ist ein Wert, der als sich selbst und nicht als der Wert einer Variablen oder das Ergebnis eines Ausdrucks, z. B. die Zahl 3 oder die Zeichenfolge "Hello" ausgedrückt wird. Eine Konstante ist, einen aussagekräftigen Namen, der tritt an die Stelle eines Literals und behält den gleichen Wert in der gesamten Anwendung, im Gegensatz zu einer Variablen, deren Wert ändern kann.  
  
 Wenn [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ist `On`, müssen Sie alle Konstanten mit einem Datentyp explizit deklarieren. Im folgenden Beispiel ist der Datentyp des `MyByte` wird als Datentyp explizit deklariert `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 Wenn `Option Infer` ist `On` oder `Option Strict` ist `Off`, Deklarieren einer Konstante können Sie ohne Angabe von einem Datentyp mit einer `As` Klausel. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Ein numerisches Ganzzahlliteral umgewandelt wird, werden standardmäßig die `Integer` -Datentyp. Der Standarddatentyp für Gleitkommazahlen ist `Double`, Schlüsselwörter und `True` und `False` Geben Sie einen `Boolean` Konstanten.  
  
## <a name="literals-and-type-coercion"></a>Literale und Typkoersion  
 In einigen Fällen empfiehlt es sich um ein Literal für einen bestimmten Datentyp zu erzwingen; z. B., wenn Sie eine Variable des Typs einer besonders großen Ganzzahlliteralwert zuweisen `Decimal`. Im folgenden Beispiel wird einen Fehler an:  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Der Fehler resultiert aus der Darstellung des Literals. Die `Decimal` -Datentyp kann einen Wert enthalten dieser Größe, aber das Literal wird implizit als dargestellt eine `Long`, welche nicht.  
  
 Sie können coerce-Literal in einen bestimmten Datentyp, gibt es zwei Möglichkeiten: ein Typzeichen, Anfügen oder legen Sie das Element innerhalb der umschließenden Zeichen. Ein Typzeichen oder Zeichen einschließen muss unmittelbar vorangestellt sein und/oder führen Sie das Literal, ohne Leerzeichen oder Zeichen jeglicher Art.  
  
 Damit wird das vorherige Beispiel funktioniert, fügen Sie der `D` Typzeichen, dem Literal, das als dargestellt wird ein `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 Das folgende Beispiel veranschaulicht die richtige Verwendung von Typzeichen und umschließenden Zeichen:  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 Die folgende Tabelle zeigt die umschließenden Zeichen und ein Typzeichen, die in Visual Basic verfügbar.  
  
|Datentyp|Zeichen|Angefügte Typzeichen|  
|---|---|---|  
|`Boolean`|(keine)|(keine)|  
|`Byte`|(keine)|(keine)|  
|`Char`|"|C|  
|`Date`|#|(keine)|  
|`Decimal`|(keine)|D oder @|  
|`Double`|(keine)|R "oder" #|  
|`Integer`|(keine)|Ich oder %|  
|`Long`|(keine)|L oder &|  
|`Short`|(keine)|S|  
|`Single`|(keine)|F oder!|  
|`String`|"|(keine)|  
  
## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [Vorgehensweise: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Option Explicit-Anweisung](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
