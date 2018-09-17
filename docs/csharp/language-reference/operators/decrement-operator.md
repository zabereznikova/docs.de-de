---
title: Operator -- (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 615b100447233856ab3740d075d69e3ae19285fd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45648781"
---
# <a name="---operator-c-reference"></a>Operator -- (C#-Referenz)
Der Dekrementoperator (`--`) verringert seinen Operanden um 1. Der Dekrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `--variable` und `variable--`. Die erste Form stellt eine Präfixdekrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, „nachdem“ er vermindert worden ist. Die zweite Form stellt eine Postfixdekrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, bevor er vermindert worden ist.  
  
## <a name="remarks"></a>Hinweise  
 Für alle numerischen Typen und Enumerationstypen sind Dekrementoperatoren vordefiniert.  
  
 Benutzerdefinierte Typen können den Operator `--` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
