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
ms.openlocfilehash: 03d693653cd166bbf1096031f1a864b492e2e896
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086295"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Konstanten und literale Datentypen (Visual Basic)

Ein Literalwert ist ein Wert, der als sich selbst und nicht als Variablen Wert oder als Ergebnis eines Ausdrucks ausgedrückt wird, z. b. die Zahl 3 oder die Zeichenfolge "Hello". Eine Konstante ist ein sinnvoller Name, der den Speicherort eines Literals annimmt und denselben Wert im gesamten Programm beibehält, im Gegensatz zu einer Variablen, deren Wert sich ändern kann.  
  
 Wenn die [Option Infer](../../../language-reference/statements/option-infer-statement.md) ist `Off` und [Option Strict](../../../language-reference/statements/option-strict-statement.md) ist `On` , müssen Sie alle Konstanten explizit mit einem-Datentyp deklarieren. Im folgenden Beispiel wird der Datentyp von `MyByte` explizit als-Datentyp deklariert `Byte` :  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 Wenn auf oder festgelegt ist `Option Infer` `On` `Option Strict` `Off` , können Sie eine Konstante deklarieren, ohne einen-Datentyp mit einer- `As` Klausel anzugeben. Der Compiler bestimmt den Typ der Konstante vom Typ des Ausdrucks. Ein numerisches Ganzzahlliteral wird standardmäßig in den- `Integer` Datentyp umgewandelt. Der Standard Datentyp für Gleit Komma Zahlen ist `Double` , und die Schlüsselwörter `True` und `False` geben eine `Boolean` Konstante an.  
  
## <a name="literals-and-type-coercion"></a>Literale und Typumwandlung  

 In einigen Fällen möchten Sie möglicherweise einen Literalwert für einen bestimmten Datentyp erzwingen. beispielsweise beim Zuweisen eines besonders großen ganzzahligen Literalwerts zu einer Variablen vom Typ `Decimal` . Im folgenden Beispiel wird ein Fehler erzeugt:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Der Fehler ergibt sich aus der Darstellung des Literals. Der- `Decimal` Datentyp kann einen Wert enthalten, der groß ist, aber das Literale wird implizit als dargestellt `Long` , was nicht möglich ist.  
  
 Sie können einen Literalwert auf zwei Arten in einen bestimmten Datentyp umwandeln: indem Sie ein Typzeichen an ihn anfügen oder ihn in einschließende Zeichen platzieren. Ein Typzeichen oder einschließende Zeichen muss unmittelbar vor und/oder nach dem Literalzeichen stehen, ohne dass dazwischen liegende Leerzeichen oder Zeichen vorhanden sind.  
  
 Damit das vorherige Beispiel funktioniert, können Sie das `D` Typzeichen an das Literale anfügen, wodurch es als dargestellt wird `Decimal` :  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 Das folgende Beispiel veranschaulicht die korrekte Verwendung von Typzeichen und einschließenden Zeichen:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 In der folgenden Tabelle werden die in Visual Basic verfügbaren einschließenden Zeichen und Typzeichen angezeigt.  
  
|Datentyp|Einschließendes Zeichen|Angefügtes Typzeichen|  
|---|---|---|  
|`Boolean`|(none)|(none)|  
|`Byte`|(none)|(none)|  
|`Char`|"|C|  
|`Date`|#|(none)|  
|`Decimal`|(none)|D oder @|  
|`Double`|(none)|R oder #|  
|`Integer`|(none)|I oder%|  
|`Long`|(none)|L oder &|  
|`Short`|(none)|E|  
|`Single`|(none)|F oder!|  
|`String`|"|(none)|  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Konstanten](user-defined-constants.md)
- [Vorgehensweise: Deklarieren einer Konstante](how-to-declare-a-constant.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
- [Option Explicit-Anweisung](../../../language-reference/statements/option-explicit-statement.md)
- [Übersicht über Enumerationen](enumerations-overview.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)
