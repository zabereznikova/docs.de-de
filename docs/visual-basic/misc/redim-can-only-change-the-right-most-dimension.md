---
title: '&#39;ReDim&#39; können nur die Dimension ganz rechts ändern'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: efb98df13a7e3e378347b30b6fc00b90030ec194
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a>&#39;ReDim&#39; können nur die Dimension ganz rechts ändern
Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist. Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern. Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Preserve` -Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Arraydimensionen in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim-Anweisung](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Beibehalten – löschen](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
