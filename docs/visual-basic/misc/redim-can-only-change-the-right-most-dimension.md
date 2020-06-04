---
title: „ReDim“ kann nur die Dimension ganz rechts ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 8e42e0df7b97fb96f468ce37dd4cfc52fad8c596
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358295"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>„ReDim“ kann nur die Dimension ganz rechts ändern.
Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist. Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern. Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie das `Preserve` -Schlüsselwort.  
  
## <a name="see-also"></a>Weitere Informationen

- [Arrays in Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Array Dimensionen in Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim-Anweisung](../language-reference/statements/redim-statement.md)
- [Dim-Anweisung](../language-reference/statements/dim-statement.md)
