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
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920639"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert Sie eine Klasse oder Struktur in einen Typ, der möglicherweise nicht alle möglichen Werte der ursprünglichen Klasse oder Struktur enthält.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Mit dem Schlüsselwort einschränkende Konvertierung  
 Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Narrowing`.  
  
 Einschränkende Konvertierungen nicht immer erfolgreich zur Laufzeit und können fehlschlagen oder Datenverlust verursachen. Beispiele sind `Long` zu `Integer`, `String` zu `Date`, und ein Basistyp für einen abgeleiteten Typ. Da es sich bei dem Basistyp entspricht möglicherweise nicht alle Member des abgeleiteten Typs enthalten und daher ist keine Instanz des abgeleiteten Typs einschränkend diesem letzten Konvertierung.  
  
 Wenn `Option Strict` ist `On`, wird die Nutzung von Code verwenden muss, `CType` für alle einschränkende Konvertierungen.  
  
 Die `Narrowing` -Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
