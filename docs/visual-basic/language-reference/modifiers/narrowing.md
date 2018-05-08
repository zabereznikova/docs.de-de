---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 54a18d0cc10e42829b48b0ef75bb77ab0d47b45f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert eine Klasse oder Struktur in einen Typ, der möglicherweise nicht in der Lage, alle möglichen Werte der ursprünglichen Klasse oder Struktur zu speichern.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Konvertieren mit dem Narrowing-Schlüsselwort  
 Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Narrowing`.  
  
 Einschränkende Konvertierungen nicht immer erfolgreich ausgeführt werden Sie, zur Laufzeit und können fehlschlagen Sie oder verursachen Sie Datenverlust. Beispiele sind `Long` auf `Integer`, `String` auf `Date`, und ein Basistyp in einen abgeleiteten Typ. Da der Basistyp möglicherweise nicht alle Member des abgeleiteten Typs enthalten und daher keine Instanz des abgeleiteten Typs ist einschränkend letzte Konvertierung.  
  
 Wenn `Option Strict` ist `On`, wird die Nutzung von Code verwenden muss `CType` für alle einschränkende Konvertierungen.  
  
 Die `Narrowing` -Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
