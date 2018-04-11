---
title: Fehlerhafte DLL-Aufrufkonvention
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
