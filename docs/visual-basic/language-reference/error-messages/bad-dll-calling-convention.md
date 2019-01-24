---
title: Fehlerhafte DLL-Aufrufkonvention
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 70200b38ea3d1497daa091fa407accabaf3c4eda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715776"
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
