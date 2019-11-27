---
title: Widening
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
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347828"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Gibt an, dass ein Konvertierungs Operator (`CType`) eine Klasse oder Struktur in einen Typ konvertiert, der alle möglichen Werte der ursprünglichen Klasse oder Struktur enthalten kann.  
  
## <a name="converting-with-the-widening-keyword"></a>Umrechnen mit dem Erweiterungs Schlüsselwort  
 In der Konvertierungs Prozedur muss zusätzlich zu `Widening``Public Shared` angegeben werden.  
  
 Erweiternde Konvertierungen sind immer zur Laufzeit erfolgreich und verursachen niemals Datenverluste. `Single` Beispiele für die `Double`, `Char` `String`und einen abgeleiteten Typ für den Basistyp. Diese letzte Konvertierung ist erweiternd, da der abgeleitete Typ alle Member des Basistyps enthält und somit eine Instanz des Basistyps ist.  
  
 Der verarbeitende Code muss nicht `CType` für erweiternde Konvertierungen verwenden, auch wenn `Option Strict` `On`ist.  
  
 Das `Widening`-Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Beispielsweise Definitionen erweiterter und einschränkende Konvertierungs Operatoren finden Sie unter Gewusst [wie: Definieren eines Konvertierungs Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Siehe auch

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
