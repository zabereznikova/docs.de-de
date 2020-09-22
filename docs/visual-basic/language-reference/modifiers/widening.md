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
ms.openlocfilehash: 14e0b026f4fc3b0bf202ea643a28d6f1a7df2b7c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867650"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)

Gibt an, dass ein Konvertierungs Operator ( `CType` ) eine Klasse oder Struktur in einen Typ konvertiert, der alle möglichen Werte der ursprünglichen Klasse oder Struktur enthalten kann.  
  
## <a name="converting-with-the-widening-keyword"></a>Umrechnen mit dem Erweiterungs Schlüsselwort  

 Die Konvertierungs Prozedur muss `Public Shared` zusätzlich zu angeben `Widening` .  
  
 Erweiternde Konvertierungen sind immer zur Laufzeit erfolgreich und verursachen niemals Datenverluste. Beispiele hierfür sind, `Single` `Double` `Char` `String` und ein abgeleiteter Typ für den Basistyp. Diese letzte Konvertierung ist erweiternd, da der abgeleitete Typ alle Member des Basistyps enthält und somit eine Instanz des Basistyps ist.  
  
 Der verarbeitende Code muss nicht `CType` für erweiternde Konvertierungen verwendet werden, auch wenn gleich `Option Strict` ist `On` .  
  
 Das `Widening` Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 Beispielsweise Definitionen erweiterter und einschränkende Konvertierungs Operatoren finden Sie unter Gewusst [wie: Definieren eines Konvertierungs Operators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Operator Statement](../statements/operator-statement.md)
- [Narrowing](narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Vorgehensweise: Definieren eines Operators](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict-Anweisung](../statements/option-strict-statement.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
