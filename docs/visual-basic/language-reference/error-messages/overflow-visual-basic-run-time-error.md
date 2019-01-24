---
title: Überlauf (Visual Basic-Laufzeitfehler)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: c45559042231b72ef1ba892cabbead03797df8e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642510"
---
# <a name="overflow-visual-basic-run-time-error"></a>Überlauf (Visual Basic-Laufzeitfehler)
Ein Überlauf tritt beim Versuch, einer Zuordnung, die die Grenzen des Ziels für die Zuweisung des überschreitet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Ergebnisse von Zuweisungen, Berechnungen und den Datentyp Konvertierungen sind nicht zu groß, um innerhalb des Bereichs von Variablen, die für diese Art von Wert zulässigen dargestellt werden, und weisen Sie den Wert einer Variablen eines Typs, die eine größere Anzahl von Werten enthalten kann , falls erforderlich.  
  
2.  Stellen Sie sicher, dass Zuweisungen zu Eigenschaften des Bereichs von der Eigenschaft entsprechen, die sie vorgenommen werden.  
  
3.  Stellen Sie sicher, dass Zahlen, die in Berechnungen, die in Zahlen umgewandelt werden, verwendet keine Ergebnisse, die größer als ganze Zahlen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
