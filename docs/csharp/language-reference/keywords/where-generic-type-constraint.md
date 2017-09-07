---
title: "where (Einschränkung des generischen Typs) (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
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
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a>where (Einschränkung des generischen Typs) (C#-Referenz)
In einer generischen Typdefinition wird die `where`-Klausel verwendet, um Einschränkungen für Typen anzugeben, die als Argumente für einen Typenparameter verwendet werden können, der in einer generischen Deklaration definiert ist. So können Sie beispielsweise eine generische Klasse erstellen, `MyGenericClass`, deren Typparameter `T` die Schnittstelle <xref:System.IComparable%601> implementiert:  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  Weitere Informationen über die where-Klausel in einem Abfrageausdruck finden Sie unter [where-Klausel](../../../csharp/language-reference/keywords/where-clause.md).  
  
 Zusätzlich zu Schnittstelleneinschränkungen kann eine `where`-Klausel eine Basisklasseneinschränkung enthalten, die angibt, dass ein Typ über die angegebene Klasse als Basisklasse verfügen muss (oder diese Klasse selbst sein muss), um als Typargument für diesen generischen Typ verwendet werden zu können. Wenn eine solche Einschränkung verwendet wird, muss sie vor jeder anderen Einschränkung für den Typparameter angezeigt werden.  
  
 [!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 Die `where`-Klausel kann auch eine Konstruktoreinschränkung einschließen. Es ist möglich, eine Instanz eines Typparameters mithilfe des neuen Operators zu erstellen. Allerdings muss zu diesem Zweck der Typparameter durch die Konstruktoreinschränkung `new()` eingeschränkt werden. Die [new()-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md) informiert den Compiler, dass jedes angegebene Typargument über einen zugänglichen parameterlosen oder Standardkonstruktor verfügen muss. Beispiel:  
  
 [!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 Die `new()`-Einschränkung wird in der `where`-Klausel als Letztes angezeigt.  
  
 Bei mehreren Typparametern müssen Sie für jeden davon eine eigene `where`-Klausel verwenden, z.B.:  
  
 [!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 Sie können auch Einschränkungen wie folgt an Typparameter generischer Methoden anfügen:  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 Beachten Sie, dass die Syntax zum Beschreiben der Parametereinschränkungen für Delegaten mit der Syntax von Methoden identisch ist:  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 Informationen zu generischen Delegaten finden Sie unter [Generic Delegates (Generische Delegaten)](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
 Weitere Informationen zur Syntax und der Verwendung von Einschränkungen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [new-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md)   
 [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

