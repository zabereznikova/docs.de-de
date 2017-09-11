---
title: sealed (C#-Referenz)
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8d0fe959eac03aad4f1ae1fada61c0ad2fd65cd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="sealed-c-reference"></a><span data-ttu-id="bed53-102">sealed (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bed53-102">sealed (C# Reference)</span></span>
<span data-ttu-id="bed53-103">Der Modifizierer `sealed` verhindert, dass andere Klassen von einer Klasse erben, wenn er auf diese Klasse angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="bed53-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="bed53-104">Im folgenden Beispiel erbt die Klasse `B` von der Klasse `A`, allerdings kann keine Klasse von der Klasse `B` erben.</span><span class="sxs-lookup"><span data-stu-id="bed53-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="bed53-105">Sie können den Modifizierer `sealed` auch auf eine Methode oder Eigenschaft anwenden, die eine virtuelle Methode oder Eigenschaft in einer Basisklasse außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="bed53-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="bed53-106">Dadurch können Sie zulassen, dass Klassen von Ihrer Klasse abgeleitet werden, und verhindern, dass sie spezifische virtuelle Methoden oder Eigenschaften außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="bed53-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed53-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bed53-107">Example</span></span>  
 <span data-ttu-id="bed53-108">Im folgenden Beispiel erbt `Z` von `Y`, `Z` kann aber die virtuelle Funktion `F` nicht außer Kraft setzen, die in `X` angegeben und in `Y` versiegelt ist.</span><span class="sxs-lookup"><span data-stu-id="bed53-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 <span data-ttu-id="bed53-109">[!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bed53-109">[!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]</span></span>  
  
 <span data-ttu-id="bed53-110">Wenn Sie neue Methoden oder Eigenschaften in einer Klasse definieren, können Sie verhindern, dass ableitende Klassen sie außer Kraft setzen, indem Sie sie nicht als [virtual](../../../csharp/language-reference/keywords/virtual.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bed53-110">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="bed53-111">Es wäre ein Fehler, den Modifizierer [abstract](../../../csharp/language-reference/keywords/abstract.md) mit einer versiegelten Klasse zu verwenden, da eine abstrakte Klasse von einer Klasse geerbt werden muss, die eine Implementierung der abstrakten Methoden oder Eigenschaften bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="bed53-111">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="bed53-112">Der Modifizierer `sealed` muss immer mit [override](../../../csharp/language-reference/keywords/override.md) verwendet werden, wenn er auf eine Methode oder Eigenschaft angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="bed53-112">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="bed53-113">Da Strukturen implizit versiegelt sind, können sie nicht geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="bed53-113">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="bed53-114">Weitere Informationen finden Sie unter [Inheritance (Vererbung)](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="bed53-114">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="bed53-115">Weitere Beispiele finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="bed53-115">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed53-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bed53-116">Example</span></span>  
 <span data-ttu-id="bed53-117">[!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bed53-117">[!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]</span></span>  
  
 <span data-ttu-id="bed53-118">Im vorherigen Beispiel können Sie mithilfe der folgenden Anweisung versuchen, von der versiegelten Klasse zu erben:</span><span class="sxs-lookup"><span data-stu-id="bed53-118">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="bed53-119">Daraus ergibt sich eine Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="bed53-119">The result is an error message:</span></span>  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="bed53-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="bed53-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="bed53-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bed53-121">Remarks</span></span>  
 <span data-ttu-id="bed53-122">Sie sollten generell die folgenden zwei Punkte in Betracht ziehen, um festzustellen, ob Sie eine Klasse, Methode oder Eigenschaft versiegeln sollten:</span><span class="sxs-lookup"><span data-stu-id="bed53-122">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="bed53-123">Die potentiellen Vorteile, die ableitende Klassen durch die Möglichkeit, Ihre Klasse anzupassen, erhalten könnten</span><span class="sxs-lookup"><span data-stu-id="bed53-123">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="bed53-124">Die Möglichkeit, dass ableitende Klassen Ihre Klassen so ändern könnten, dass sie nicht mehr korrekt oder wie erwartet funktionieren</span><span class="sxs-lookup"><span data-stu-id="bed53-124">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed53-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bed53-125">See Also</span></span>  
 <span data-ttu-id="bed53-126">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bed53-127">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bed53-128">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bed53-129">[Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-129">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 <span data-ttu-id="bed53-130">[Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-130">[Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
 <span data-ttu-id="bed53-131">[Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-131">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="bed53-132">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-132">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="bed53-133">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="bed53-133">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="bed53-134">virtual</span><span class="sxs-lookup"><span data-stu-id="bed53-134">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)

