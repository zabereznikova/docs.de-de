---
title: Überlauf (Visual Basic-Laufzeitfehler)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871221"
---
# <a name="overflow-visual-basic-run-time-error"></a>Überlauf (Visual Basic-Laufzeitfehler)

Ein Überlauf Ergebnis, wenn Sie versuchen, eine Zuweisung durchführen, die die Grenzwerte für das Ziel der Zuweisung überschreitet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass die Ergebnisse von Zuweisungen, Berechnungen und Datentyp Konvertierungen nicht zu groß sind, um innerhalb des Bereichs von Variablen, die für diesen Werttyp zulässig sind, dargestellt zu werden, und weisen Sie den Wert einer Variablen eines Typs zu, die ggf. einen größeren Wertebereich enthalten kann.  
  
2. Stellen Sie sicher, dass die Zuweisungen von Eigenschaften dem Bereich der Eigenschaft entsprechen, an der Sie vorgenommen werden.  
  
3. Stellen Sie sicher, dass die Zahlen, die in Berechnungen verwendet werden, die in ganze Zahlen umgewandelt werden, keine Ergebnisse aufweisen, die größer als ganze Zahlen sind.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Datentypen](../data-types/index.md)
- [Fehlertypen](../../programming-guide/language-features/error-types.md)
