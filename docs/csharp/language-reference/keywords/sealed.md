---
title: sealed (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a546a6019daf836ab870775e4432660aa723fd69
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="sealed-c-reference"></a>sealed (C#-Referenz)
Der Modifizierer `sealed` verhindert, dass andere Klassen von einer Klasse erben, wenn er auf diese Klasse angewendet wird. Im folgenden Beispiel erbt die Klasse `B` von der Klasse `A`, allerdings kann keine Klasse von der Klasse `B` erben.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 Sie können den Modifizierer `sealed` auch auf eine Methode oder Eigenschaft anwenden, die eine virtuelle Methode oder Eigenschaft in einer Basisklasse außer Kraft setzt. Dadurch können Sie zulassen, dass Klassen von Ihrer Klasse abgeleitet werden, und verhindern, dass sie spezifische virtuelle Methoden oder Eigenschaften außer Kraft setzen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel erbt `Z` von `Y`, `Z` kann aber die virtuelle Funktion `F` nicht außer Kraft setzen, die in `X` angegeben und in `Y` versiegelt ist.  
  
 [!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 Wenn Sie neue Methoden oder Eigenschaften in einer Klasse definieren, können Sie verhindern, dass ableitende Klassen sie außer Kraft setzen, indem Sie sie nicht als [virtual](../../../csharp/language-reference/keywords/virtual.md) deklarieren.  
  
 Es wäre ein Fehler, den Modifizierer [abstract](../../../csharp/language-reference/keywords/abstract.md) mit einer versiegelten Klasse zu verwenden, da eine abstrakte Klasse von einer Klasse geerbt werden muss, die eine Implementierung der abstrakten Methoden oder Eigenschaften bereitstellt.  
  
 Der Modifizierer `sealed` muss immer mit [override](../../../csharp/language-reference/keywords/override.md) verwendet werden, wenn er auf eine Methode oder Eigenschaft angewendet wird.  
  
 Da Strukturen implizit versiegelt sind, können sie nicht geerbt werden.  
  
 Weitere Informationen finden Sie unter [Inheritance (Vererbung)](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Weitere Beispiele finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 Im vorherigen Beispiel können Sie mithilfe der folgenden Anweisung versuchen, von der versiegelten Klasse zu erben:  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 Daraus ergibt sich eine Fehlermeldung:  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a>Hinweise  
 Sie sollten generell die folgenden zwei Punkte in Betracht ziehen, um festzustellen, ob Sie eine Klasse, Methode oder Eigenschaft versiegeln sollten:  
  
-   Die potentiellen Vorteile, die ableitende Klassen durch die Möglichkeit, Ihre Klasse anzupassen, erhalten könnten  
  
-   Die Möglichkeit, dass ableitende Klassen Ihre Klassen so ändern könnten, dass sie nicht mehr korrekt oder wie erwartet funktionieren  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)
