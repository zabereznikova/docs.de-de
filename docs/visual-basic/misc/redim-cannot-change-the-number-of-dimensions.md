---
title: ReDim kann die Anzahl der Dimensionen nicht ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b2404927c2faf30d1d058d2163fd5d67e1a52e1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358166"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>ReDim kann die Anzahl der Dimensionen nicht ändern.
Ein Vorgang versucht über die `ReDim` -Anweisung, den Rang (Anzahl von Dimensionen) eines Arrays zu ändern. `ReDim` kann die Größe einer oder mehrerer Dimensionen eines Arrays ändern, das bereits formal deklariert wurde, kann aber nicht den Rang eines Arrays ändern.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Vergewissern Sie sich, dass Sie den Rang des Arrays und nicht die Größen seiner Dimensionen ändern möchten, und verwenden Sie, sofern möglich, `Dim` , um ein neues Array mit dem gewünschten Rang zu deklarieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Arrays in Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Array Dimensionen in Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim-Anweisung](../language-reference/statements/redim-statement.md)
- [Dim-Anweisung](../language-reference/statements/dim-statement.md)
