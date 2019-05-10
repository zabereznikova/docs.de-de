---
title: ReDim kann die Anzahl der Dimensionen nicht ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 1e9695bbc7f104aa741de232f1f6d3c76df2cebf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591746"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>ReDim kann die Anzahl der Dimensionen nicht ändern.
Ein Vorgang versucht über die `ReDim` -Anweisung, den Rang (Anzahl von Dimensionen) eines Arrays zu ändern. `ReDim` kann die Größe einer oder mehrerer Dimensionen eines Arrays ändern, das bereits formal deklariert wurde, kann aber nicht den Rang eines Arrays ändern.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Vergewissern Sie sich, dass Sie den Rang des Arrays und nicht die Größen seiner Dimensionen ändern möchten, und verwenden Sie, sofern möglich, `Dim` , um ein neues Array mit dem gewünschten Rang zu deklarieren.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Arraydimensionen in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim-Anweisung](../../visual-basic/language-reference/statements/redim-statement.md)
- [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)
