---
title: "Operator ++ (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6deb2f772fefc93020e7eaaed6be35e48b11df7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operator ++ (C#-Referenz)
Der Inkrementoperator (`++`) erhöht seinen Operanden um 1. Der Inkrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `++variable` und `variable++`.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Form stellt eine Präfixinkrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, nachdem er erhöht worden ist.  
  
 Die zweite Form stellt eine Postfixinkrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, bevor er erhöht wird.  
  
 Für alle numerischen Typen und Enumerationstypen sind Inkrementoperatoren vordefiniert. Benutzerdefinierte Typen können den Operator `++` überladen. Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
