---
title: ?? Operator (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ??_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: de2abc6830419c368c6a62dfd74fc6f2013db9d4
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="-operator-c-reference"></a>?? Operator (C#-Referenz)
Der Operator `??` wird NULL-Sammeloperator genannt.  Der linke Operand wird zurückgegeben, falls dieser nicht NULL ist. Andernfalls wird der rechte Operand zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Ein Typ, der NULL-Werte zulässt, kann einen Wert aus der Domäne des Typs repräsentieren, oder der Wert kann nicht definiert sein (in diesem Fall ist der Wert NULL). Sie können mit der syntaktischen Ausdruckskraft des `??`-Operators einen entsprechenden Wert (den rechten Operand) zurückgeben, wenn der linke Operand einen Typ aufweist, der NULL-Werte zulässt und dessen Wert NULL ist. Der Versuch, einen Werttyp, der auf NULL festgelegt werden kann, einem Werttyp, der nicht auf NULL festgelegt werden kann, ohne Verwendung des Operators `??` zuzuweisen, verursacht einen Kompilierungsfehler. Wenn bei einer Typumwandlung der Werttyp, der auf NULL festgelegt werden kann, aktuell nicht definiert ist, wird eine `InvalidOperationException`-Ausnahme ausgelöst.  
  
 Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Das Ergebnis eines ?? -Operators wird nicht als Konstante angesehen, auch wenn beide Argumente Konstanten sind.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [What exactly does 'lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382) (Was genau bedeutet „Lifted“?)
