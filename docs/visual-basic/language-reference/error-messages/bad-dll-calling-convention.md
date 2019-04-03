---
title: Fehlerhafte DLL-Aufrufkonvention
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: c4f9917a7fb807cf7da92a3bba2d3edec8045bd2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813519"
---
# <a name="bad-dll-calling-convention"></a>Fehlerhafte DLL-Aufrufkonvention
Argumente, die an eine Dynamic Link Library (DLL) müssen genau mit den erwarteten, von der Routine übereinstimmen. Aufrufkonventionen befassen sich mit Anzahl, Typ und Reihenfolge der Argumente. Das Programm kann eine Routine in einer DLL aufrufen, der den falschen Typ oder die Anzahl von Argumenten übergeben wird.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass alle Argumenttypen akzeptieren, mit denen angegeben wird, in der Deklaration der Routine, die Sie aufrufen.  
  
2.  Stellen Sie sicher, dass Sie die gleiche Anzahl von Argumenten angegeben werden, in der Deklaration der Routine, die Sie aufrufen übergeben.  
  
3.  Wenn die DLL-Routine Argumente als Wert erwartet, stellen Sie sicher, dass `ByVal` für diese Argumente in der Deklaration für die Routine angegeben wird.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md)
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
