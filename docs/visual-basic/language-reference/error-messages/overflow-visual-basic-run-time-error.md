---
title: Überlauf (Visual Basic-Laufzeitfehler)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 63223a815e1c4ff8d4e0afbb6c732fff90aad465
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345546"
---
# <a name="overflow-visual-basic-run-time-error"></a>Überlauf (Visual Basic-Laufzeitfehler)
Ein Überlauf tritt beim Versuch, einer Zuordnung, die die Grenzen des Ziels für die Zuweisung des überschreitet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass die Ergebnisse von Zuweisungen, Berechnungen und den Datentyp Konvertierungen sind nicht zu groß, um innerhalb des Bereichs von Variablen, die für diese Art von Wert zulässigen dargestellt werden, und weisen Sie den Wert einer Variablen eines Typs, die eine größere Anzahl von Werten enthalten kann , falls erforderlich.  
  
2. Stellen Sie sicher, dass Zuweisungen zu Eigenschaften des Bereichs von der Eigenschaft entsprechen, die sie vorgenommen werden.  
  
3. Stellen Sie sicher, dass Zahlen, die in Berechnungen, die in Zahlen umgewandelt werden, verwendet keine Ergebnisse, die größer als ganze Zahlen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
