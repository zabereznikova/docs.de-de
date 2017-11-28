---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 16bc2fa650031d2b1f6cfaf7d128ba487963f707
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp;-Operator (C#-Referenz)
Der bedingte AND-Operator (`&&`) führt eine logische AND-Verknüpfung seiner `bool`-Operanden durch, wertet aber falls erforderlich nur den zweiten Operanden aus.  
  
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
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
