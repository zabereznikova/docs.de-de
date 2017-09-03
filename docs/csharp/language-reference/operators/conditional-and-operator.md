---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1da61947cbc85e5b3045513e99e013d1e4fae4b3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp;-Operator (C#-Referenz)
Der bedingte AND-Operator (`&&`) führt eine logische AND-Verknüpfung seiner `bool`-Operanden durch, wertet den zweiten Operanden aber nur dann aus, wenn es erforderlich ist.  
  
## <a name="remarks"></a>Hinweise  
 Der Vorgang  
  
```  
x && y  
```  
  
 entspricht dem Vorgang  
  
```  
x & y  
```  
  
 mit der Ausnahme, dass `y` nicht ausgewertet wird, wenn `x` `false` ist, weil das Ergebnis der AND-Operation `false` ist, unabhängig vom Wert von `y`. Dies wird als „Kurzschlussauswertung“ bezeichnet.  
  
 Der bedingte AND-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [true](../../../csharp/language-reference/keywords/true.md) und [false](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wertet der bedingte Ausdruck in der zweiten `if`-Anweisung nur den ersten Operanden aus, da der Operand `false` zurückgibt.  
  
 [!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)

