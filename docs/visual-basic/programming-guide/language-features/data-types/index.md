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
ms.openlocfilehash: 928d7fb6a40873641ae3e91e057c272b946a0091
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393714"
---
# <a name="data-types-in-visual-basic"></a>Datentypen in Visual Basic
Der *Datentyp* eines Programmierelements weist darauf hin, welche Art von Daten es enthalten kann, und wie es diese Daten speichert. Datentypen gelten für alle Werte, die im Arbeitsspeicher des Computers gespeichert werden oder an der Auswertung eines Ausdrucks teilnehmen können. Jeder Variablen-, Literal-, Konstanten-, Enumerations-, Eigenschafts-, Prozedurparameter-, Prozedurarguments- und Prozedurrückgabewert hat einen Datentyp.  
  
## <a name="declared-data-types"></a>Deklarierte Datentypen  
 Sie definieren ein Programmierelement mit einer Deklarationsanweisung und geben seinen Datentyp mit der `As`-Klausel an. Die folgende Tabelle zeigt die Anweisungen, die Sie verwenden, um verschiedene Elemente zu deklarieren.  
  
|Programmierelement|Datentypdeklaration|  
|-------------------------|---------------------------|  
|Variable|In einer [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|Mit einem Literalzeichen; siehe „Literalzeichen“ in [Type Characters (Visual Basic)](type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Konstante|In einer [Const-Anweisung](../../../language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Enumeration|In einer [Enum-Anweisung](../../../language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Eigenschaft|In einer [Property-Anweisung](../../../language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Prozedurparameter|In einer [Sub-Anweisung](../../../language-reference/statements/sub-statement.md), [Function-Anweisung](../../../language-reference/statements/function-statement.md) oder [Operator-Anweisung](../../../language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Prozedurargument|Im aufrufenden Code; jedes Argument ist ein Programmierelement, das bereits deklariert wurde, oder ein deklarierte Elemente enthaltender Ausdruck.<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Prozedurrückgabewert|In einer [Function-Anweisung](../../../language-reference/statements/function-statement.md) oder [Operator-Anweisung](../../../language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Eine Liste der Visual Basic-Datentypen finden Sie unter [Data Type Summary (Visual Basic)](../../../language-reference/data-types/index.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Typzeichen](type-characters.md)
- [Elementare Datentypen](elementary-data-types.md)
- [Zusammengesetzte Datentypen](composite-data-types.md)
- [Generische Typen in Visual Basic (Visual Basic)](generic-types.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Strukturen](structures.md)
- [Tupel](tuples.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Effiziente Verwendung von Datentypen](efficient-use-of-data-types.md)
