---
title: Operator ++ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46580069"
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

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
