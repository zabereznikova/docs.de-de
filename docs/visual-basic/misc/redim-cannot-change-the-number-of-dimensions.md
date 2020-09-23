---
title: ReDim kann die Anzahl der Dimensionen nicht ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077370"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>ReDim kann die Anzahl der Dimensionen nicht ändern.

Ein Vorgang versucht über die `ReDim` -Anweisung, den Rang (Anzahl von Dimensionen) eines Arrays zu ändern. `ReDim` kann die Größe einer oder mehrerer Dimensionen eines Arrays ändern, das bereits formal deklariert wurde, kann aber nicht den Rang eines Arrays ändern.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Vergewissern Sie sich, dass Sie den Rang des Arrays und nicht die Größen seiner Dimensionen ändern möchten, und verwenden Sie, sofern möglich, `Dim` , um ein neues Array mit dem gewünschten Rang zu deklarieren.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays in Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Array Dimensionen in Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim-Anweisung](../language-reference/statements/redim-statement.md)
- [Dim-Anweisung](../language-reference/statements/dim-statement.md)
