---
title: Datentypen
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
ms.openlocfilehash: 01529b36a68b8db6febb80b69a7bd81486a47087
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346346"
---
# <a name="data-types-in-visual-basic"></a>Datentypen in Visual Basic
Der *Datentyp* eines Programmierelements weist darauf hin, welche Art von Daten es enthalten kann, und wie es diese Daten speichert. Datentypen gelten für alle Werte, die im Arbeitsspeicher des Computers gespeichert werden oder an der Auswertung eines Ausdrucks teilnehmen können. Jeder Variablen-, Literal-, Konstanten-, Enumerations-, Eigenschafts-, Prozedurparameter-, Prozedurarguments- und Prozedurrückgabewert hat einen Datentyp.  
  
## <a name="declared-data-types"></a>Deklarierte Datentypen  
 Sie definieren ein Programmierelement mit einer Deklarationsanweisung und geben seinen Datentyp mit der `As`-Klausel an. Die folgende Tabelle zeigt die Anweisungen, die Sie verwenden, um verschiedene Elemente zu deklarieren.  
  
|Programmierelement|Datentypdeklaration|  
|-------------------------|---------------------------|  
|Variable|In einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|Mit einem Literalzeichen; siehe „Literalzeichen“ in [Type Characters (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Konstante|In einer [Const-Anweisung](../../../../visual-basic/language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Enumeration|In einer [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Eigenschaft|In einer [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Prozedurparameter|In einer [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) oder [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Prozedurargument|Im aufrufenden Code; jedes Argument ist ein Programmierelement, das bereits deklariert wurde, oder ein deklarierte Elemente enthaltender Ausdruck.<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Prozedurrückgabewert|In einer [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) oder [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Eine Liste der Visual Basic-Datentypen finden Sie unter [Data Type Summary (Visual Basic)](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Tupel](tuples.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
