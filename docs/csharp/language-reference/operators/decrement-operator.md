---
title: "Operator -- (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4eb68143103d44defeac7191e7c4ce7d1ee90e9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="---operator-c-reference"></a>Operator -- (C#-Referenz)
Der Dekrementoperator (`--`) verringert seinen Operanden um 1. Der Dekrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `--variable` und `variable--`. Die erste Form stellt eine Präfixdekrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, „nachdem“ er vermindert worden ist. Die zweite Form stellt eine Postfixdekrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, bevor er vermindert worden ist.  
  
## <a name="remarks"></a>Hinweise  
 Für alle numerischen Typen und Enumerationstypen sind Dekrementoperatoren vordefiniert.  
  
 Benutzerdefinierte Typen können den Operator `--` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
