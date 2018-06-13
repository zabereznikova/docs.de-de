---
title: Fehlerhafte DLL-Aufrufkonvention
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: d8c7f7aea46162215115689305f4010cb513b020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583837"
---
# <a name="bad-dll-calling-convention"></a>Fehlerhafte DLL-Aufrufkonvention
Weitergegebenen Argumenten um eine Dynamic Link Library (DLL) müssen genau mit denen von der Routine erwartet entsprechen. Aufrufkonventionen befassen sich mit Anzahl, Typ und die Reihenfolge der Argumente. Das Programm möglicherweise eine Routine in einer DLL aufrufen, der den falschen Typ oder die Anzahl von Argumenten übergeben wird.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass alle Argumenttypen stimmen mit denen angegeben wird, in der Deklaration der Routine, die Sie aufrufen.  
  
2.  Stellen Sie sicher, dass Sie die gleiche Anzahl von Argumenten angegeben werden, in der Deklaration der Routine, die Sie aufrufen übergeben werden.  
  
3.  Wenn die DLL-Routine Argumente nach Wert erwartet wird, stellen Sie sicher `ByVal` für diese Argumente in der Deklaration für die Routine angegeben ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
