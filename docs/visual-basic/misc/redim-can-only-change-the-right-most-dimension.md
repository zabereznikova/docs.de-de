---
title: „ReDim“ kann nur die Dimension ganz rechts ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 5b4f054c5d1dfad52ce19e1a9f9d246945866703
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767392"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>„ReDim“ kann nur die Dimension ganz rechts ändern.
Eine `ReDim`-Anweisung hat versucht, mithilfe des `Preserve`-Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist. Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern. Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Preserve` -Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Arraydimensionen in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim-Anweisung](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Beibehalten – Löschen](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
