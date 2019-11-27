---
title: Konstanten und literale Datentypen
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333729"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Konstanten und literale Datentypen (Visual Basic)
Ein Literalwert ist ein Wert, der als sich selbst und nicht als Variablen Wert oder als Ergebnis eines Ausdrucks ausgedrückt wird, z. b. die Zahl 3 oder die Zeichenfolge "Hello". Eine Konstante ist ein sinnvoller Name, der den Speicherort eines Literals annimmt und denselben Wert im gesamten Programm beibehält, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.  
  
 Wenn die [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) `Off` und [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`ist, müssen Sie alle Konstanten explizit mit einem-Datentyp deklarieren. Im folgenden Beispiel wird der Datentyp von `MyByte` explizit als Datentyp `Byte`deklariert:  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 Wenn `Option Infer` `On` oder `Option Strict` `Off`ist, können Sie eine Konstante deklarieren, ohne einen-Datentyp mit einer `As`-Klausel anzugeben. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Ein numerisches Ganzzahlliteral wird standardmäßig in den `Integer`-Datentyp umgewandelt. Der Standard Datentyp für Gleit Komma Zahlen ist `Double`, und die Schlüsselwörter `True` und `False` geben eine `Boolean` Konstante an.  
  
## <a name="literals-and-type-coercion"></a>Literale und Typumwandlung  
 In einigen Fällen möchten Sie möglicherweise einen Literalwert für einen bestimmten Datentyp erzwingen. beispielsweise beim Zuweisen eines besonders großen ganzzahligen Literalwerts zu einer Variablen vom Typ `Decimal`. Im folgenden Beispiel wird ein Fehler erzeugt:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Der Fehler ergibt sich aus der Darstellung des Literals. Der `Decimal`-Datentyp kann einen großen Wert enthalten, aber das Literale wird implizit als `Long`dargestellt, was nicht möglich ist.  
  
 Sie können einen Literalwert auf zwei Arten in einen bestimmten Datentyp umwandeln: indem Sie ein Typzeichen an ihn anfügen oder ihn in einschließende Zeichen platzieren. Ein Typzeichen oder einschließende Zeichen muss unmittelbar vor und/oder nach dem Literalzeichen stehen, ohne dass dazwischen liegende Leerzeichen oder Zeichen vorhanden sind.  
  
 Damit das vorherige Beispiel funktioniert, können Sie das `D` Typzeichen an das Literalzeichen anfügen, wodurch es als `Decimal`dargestellt wird:  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 Das folgende Beispiel veranschaulicht die korrekte Verwendung von Typzeichen und einschließenden Zeichen:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 In der folgenden Tabelle werden die in Visual Basic verfügbaren einschließenden Zeichen und Typzeichen angezeigt.  
  
|Datentyp|Einschließendes Zeichen|Angefügtes Typzeichen|  
|---|---|---|  
|`Boolean`|(Keine)|(Keine)|  
|`Byte`|(Keine)|(Keine)|  
|`Char`|"|A|  
|`Date`|#|(Keine)|  
|`Decimal`|(Keine)|D oder @|  
|`Double`|(Keine)|R oder #|  
|`Integer`|(Keine)|I oder%|  
|`Long`|(Keine)|L oder &|  
|`Short`|(Keine)|S|  
|`Single`|(Keine)|F oder!|  
|`String`|"|(Keine)|  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [Gewusst wie: Deklarieren einer Konstante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Option Explicit-Anweisung](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
