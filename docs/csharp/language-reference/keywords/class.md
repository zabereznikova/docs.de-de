---
title: class (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- class_CSharpKeyword
- class
dev_langs:
- CSharp
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: 02491e64813f84d031debdca09161d88aab1b94c
ms.contentlocale: de-de
ms.lasthandoff: 05/15/2017

---
# <a name="class-c-reference"></a>class (C#-Referenz)
Klassen werden mithilfe des Schlüsselworts `class` deklariert, wie im folgenden Beispiel dargestellt:  
  
```  
      class TestClass  
{  
    // Methods, properties, fields, events, delegates   
    // and nested classes go here.  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 In C# ist nur die einfache Vererbung zulässig. Eine Klasse kann also Implementierungen aus nur einer Basisklasse erben. Es kann allerdings mehr als eine Schnittstelle implementiert werden. Die folgende Tabelle zeigt Beispiele für Klassenvererbung und Implementierung der Schnittstelle:  
  
|Vererbung|Beispiel|  
|-----------------|-------------|  
|Keine|`class ClassA { }`|  
|Single|`class DerivedClass: BaseClass { }`|  
|Keine, Implementierung von zwei Schnittstellen|`class ImplClass: IFace1, IFace2 { }`|  
|Single, Implementierung einer Schnittstelle|`class ImplDerivedClass: BaseClass, IFace1 { }`|  
  
 Klassen, die Sie direkt innerhalb eines Namespace und nicht in anderen Klassen geschachtelt deklarieren, können entweder [public](../../../csharp/language-reference/keywords/public.md) oder [internal](../../../csharp/language-reference/keywords/internal.md) sein. Klassen sind standardmäßig `internal`.  
  
 Klassenmember, einschließlich geschachtelter Klassen und Strukturen, können [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder [private](../../../csharp/language-reference/keywords/private.md) sein. Member sind standardmäßig [private](../../../csharp/language-reference/keywords/private.md).  
  
 Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Sie können generische Klassen deklarieren, die über Typparameter verfügen. Weitere Informationen finden Sie unter [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md).  
  
 Eine Klasse kann Deklarationen der folgenden Member enthalten:  
  
-   [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)  

-   [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [Indexer](../../../csharp/programming-guide/indexers/index.md)  
  
-   [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [Ereignisse](../../../csharp/programming-guide/events/index.md)  
  
-   [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
  
-   [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Deklarieren von Klassenfeldern, Konstruktoren und Methoden. Darüber hinaus veranschaulicht es Objektinstanziierung und Ausgabe von Instanzdaten. In diesem Beispiel werden zwei Klassen deklariert. Die `Child`-Klasse enthält zwei private Felder (`name` und `age`) sowie zwei öffentliche Methoden. Die zweite Klasse, `StringTest`, enthält `Main`.  
  
 [!code-cs[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]  
  
## <a name="comments"></a>Kommentare  
 Beachten Sie im vorherigen Beispiel, dass auf die privaten Felder (`name` und `age`) nur über die öffentlichen Methoden der `Child`-Klasse zugegriffen werden kann. Sie können z.B. den Namen des untergeordneten Elements nicht aus der `Main`-Methode mit einer Anweisung wie folgt drucken:  
  
```  
Console.Write(child1.name);   // Error  
```  
  
 Zugriff auf private Member der `Child` von `Main` wäre nur möglich, wenn `Main` ein Member der Klasse wäre.  
  
 Typen, die innerhalb einer Klasse ohne Zugriffsmodifizierer deklariert werden, sind standardmäßig `private`, sodass die Datenmember in diesem Beispiel dennoch `private` wären, wenn das Schlüsselwort entfernt worden wäre.  
  
 Beachten Sie schließlich, dass für das Objekt, das mit dem Standardkonstruktor (`child3`) erstellt wurde, das Altersfeld standardmäßig auf 0 initialisiert wurde.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)

