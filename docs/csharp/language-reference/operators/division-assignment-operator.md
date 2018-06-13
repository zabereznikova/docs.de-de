---
title: Operator /= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171620"
---
# <a name="-operator-c-reference"></a>Operator /= (C#-Referenz)
Der Divisionszuweisungsoperator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `/=`, z.B.  
  
```csharp  
x /= y  
```  
  
 für die folgende Syntax:  
  
```csharp  
x = x / y  
```  
  
 außer dass `x` nur einmal überprüft wird. Die [/ operator](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen vordefiniert, um Division auszuführen.  
  
 Der Operator `/=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[/ operator](../../../csharp/language-reference/operators/division-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Bei allen Zusammensetzungszuweisungsoperatoren wird die entsprechende Verbundzuweisung durch das Überladen des binären Operators implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
