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
ms.openlocfilehash: d7d43d4f5f931881d5c8b663c719fe7f92559799
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825312"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert Sie eine Klasse oder Struktur in einen Typ, der alle möglichen Werte der ursprünglichen Klasse oder Struktur enthalten kann.  
  
## <a name="converting-with-the-widening-keyword"></a>Konvertierung mit dem Widening-Schlüsselwort  
 Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Widening`.  
  
 Erweiternde Konvertierungen immer erfolgreich, zur Laufzeit und verursachen keine Daten verloren gehen. Beispiele sind `Single` zu `Double`, `Char` zu `String`, und einen abgeleiteten Typ in den Basistyp. Die letzte Konvertierung ist erweiternde, weil der abgeleitete Typ alle Member des Basistyps enthält und daher eine Instanz des Basistyps.  
  
 Der konsumierenden Code keine Verwendung `CType` für erweiternde Konvertierungen, auch wenn `Option Strict` ist `On`.  
  
 Die `Widening` -Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Definitionen von erweiternde und eingrenzende Konvertierungsoperatoren, z. B. finden Sie unter [Vorgehensweise: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Siehe auch

- [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
