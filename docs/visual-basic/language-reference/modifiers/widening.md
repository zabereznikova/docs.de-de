---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 2323aa38c81ce4e027f256d0e29c069f7ec77c00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert eine Klasse oder Struktur in einen Typ, der alle möglichen Werte der ursprünglichen Klasse oder Struktur aufnehmen kann.  
  
## <a name="converting-with-the-widening-keyword"></a>Konvertieren mit dem Widening-Schlüsselwort  
 Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Widening`.  
  
 Erweiternde Konvertierungen zur Laufzeit immer erfolgreich sein und Verlust von Daten niemals anfallen. Beispiele sind `Single` auf `Double`, `Char` auf `String`, und ein abgeleiteter Typ mit seinem Basistyp. Diese letzte Konvertierung ist erweiternd, weil der abgeleitete Typ alle Member des Basistyps enthält und daher eine Instanz des Basistyps ist.  
  
 Der verwendete Code muss keine verwenden `CType` für erweiterungskonvertierungen, selbst wenn `Option Strict` ist `On`.  
  
 Die `Widening` -Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Definitionen der erweiternde und eingrenzende Konvertierungsoperatoren, z. B. finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
