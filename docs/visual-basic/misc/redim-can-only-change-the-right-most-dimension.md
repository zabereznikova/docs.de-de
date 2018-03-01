---
title: "&#39; ReDim &#39; Die Dimension ganz rechts kann nur geändert werden."
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a>&#39; ReDim &#39; Die Dimension ganz rechts kann nur geändert werden.
Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist. Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern. Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Preserve` -Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Arraydimensionen in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim-Anweisung](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Beibehalten – löschen](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
