---
title: /= Operator (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bd9cb025153897c2c9b47a606f0d78d8ea4ad488
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>Operator /= (C#-Referenz)
Der Divisionszuweisungsoperator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `/=`, z.B.  
  
```  
x /= y  
```  
  
 für die folgende Syntax:  
  
```  
x = x / y  
```  
  
 außer dass `x` nur einmal überprüft wird. Die [/ operator](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen vordefiniert, um Division auszuführen.  
  
 Der Operator `/=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[/ operator](../../../csharp/language-reference/operators/division-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Bei allen Zusammensetzungszuweisungsoperatoren wird die entsprechende Verbundzuweisung durch das Überladen des binären Operators implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)

