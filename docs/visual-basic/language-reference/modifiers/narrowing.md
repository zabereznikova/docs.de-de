---
title: Narrowing
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
ms.openlocfilehash: b252f7939e812f31103d4bd98ffd50953679f042
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351475"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Gibt an, dass ein Konvertierungs Operator (`CType`) eine Klasse oder Struktur in einen Typ konvertiert, der möglicherweise nicht in der Lage ist, einige der möglichen Werte der ursprünglichen Klasse oder Struktur zu speichern.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Umrechnen mit dem einschränkenden Schlüsselwort  
 In der Konvertierungs Prozedur muss zusätzlich zu `Narrowing``Public Shared` angegeben werden.  
  
 Einschränkende Konvertierungen sind zur Laufzeit nicht immer erfolgreich und können fehlschlagen oder Datenverluste verursachen. Beispiele sind `Long`, `Integer`, `String` `Date`und einen Basistyp auf einen abgeleiteten Typ zu. Diese letzte Konvertierung ist einschränkend, weil der Basistyp möglicherweise nicht alle Member des abgeleiteten Typs enthält und somit keine Instanz des abgeleiteten Typs ist.  
  
 Wenn `Option Strict` `On`ist, muss der verarbeitende Code `CType` für alle einschränkenden Konvertierungen verwenden.  
  
 Das `Narrowing`-Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
