---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 15bb3e9702f04cc805af63767c7ecbfc68160368
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171914"
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp;-Operator (C#-Referenz)
Der bedingte AND-Operator (`&&`) führt eine logische AND-Verknüpfung seiner `bool`-Operanden durch, wertet aber falls erforderlich nur den zweiten Operanden aus.  
  
## <a name="remarks"></a>Hinweise  
 Der Vorgang  
  
```csharp  
x && y  
```  
  
 entspricht dem Vorgang  
  
```csharp  
x & y  
```  
  
 mit der Ausnahme, dass `y` nicht ausgewertet wird, wenn `x` `false` ist, weil das Ergebnis der AND-Operation `false` ist, unabhängig vom Wert von `y`. Dies wird als „Kurzschlussauswertung“ bezeichnet.  
  
 Der bedingte AND-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [true](../../../csharp/language-reference/keywords/true.md) und [false](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wertet der bedingte Ausdruck in der zweiten `if`-Anweisung nur den ersten Operanden aus, da der Operand `false` zurückgibt.  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
