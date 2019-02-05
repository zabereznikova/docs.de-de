---
title: „ReDim“ kann nur die Dimension ganz rechts ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: d20d0374cd5183b6216d1c6e5b138256cf0a4f17
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738954"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>„ReDim“ kann nur die Dimension ganz rechts ändern.
Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist. Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern. Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Preserve` -Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch
- [Arrays in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Arraydimensionen in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim-Anweisung](../../visual-basic/language-reference/statements/redim-statement.md)
- [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)
