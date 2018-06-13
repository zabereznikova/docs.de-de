---
title: sealed (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: bd4fe2cfe80930c121a11d03c848b2c4eca152d6
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172122"
---
# <a name="sealed-c-reference"></a><span data-ttu-id="1588c-102">sealed (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1588c-102">sealed (C# Reference)</span></span>
<span data-ttu-id="1588c-103">Der Modifizierer `sealed` verhindert, dass andere Klassen von einer Klasse erben, wenn er auf diese Klasse angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1588c-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="1588c-104">Im folgenden Beispiel erbt die Klasse `B` von der Klasse `A`, allerdings kann keine Klasse von der Klasse `B` erben.</span><span class="sxs-lookup"><span data-stu-id="1588c-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```csharp  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="1588c-105">Sie können den Modifizierer `sealed` auch auf eine Methode oder Eigenschaft anwenden, die eine virtuelle Methode oder Eigenschaft in einer Basisklasse außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="1588c-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="1588c-106">Dadurch können Sie zulassen, dass Klassen von Ihrer Klasse abgeleitet werden, und verhindern, dass sie spezifische virtuelle Methoden oder Eigenschaften außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="1588c-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1588c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1588c-107">Example</span></span>  
 <span data-ttu-id="1588c-108">Im folgenden Beispiel erbt `Z` von `Y`, `Z` kann aber die virtuelle Funktion `F` nicht außer Kraft setzen, die in `X` angegeben und in `Y` versiegelt ist.</span><span class="sxs-lookup"><span data-stu-id="1588c-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 <span data-ttu-id="1588c-109">Wenn Sie neue Methoden oder Eigenschaften in einer Klasse definieren, können Sie verhindern, dass ableitende Klassen sie außer Kraft setzen, indem Sie sie nicht als [virtual](../../../csharp/language-reference/keywords/virtual.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1588c-109">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="1588c-110">Es wäre ein Fehler, den Modifizierer [abstract](../../../csharp/language-reference/keywords/abstract.md) mit einer versiegelten Klasse zu verwenden, da eine abstrakte Klasse von einer Klasse geerbt werden muss, die eine Implementierung der abstrakten Methoden oder Eigenschaften bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1588c-110">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="1588c-111">Der Modifizierer `sealed` muss immer mit [override](../../../csharp/language-reference/keywords/override.md) verwendet werden, wenn er auf eine Methode oder Eigenschaft angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1588c-111">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="1588c-112">Da Strukturen implizit versiegelt sind, können sie nicht geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="1588c-112">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="1588c-113">Weitere Informationen finden Sie unter [Inheritance (Vererbung)](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="1588c-113">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="1588c-114">Weitere Beispiele finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="1588c-114">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1588c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1588c-115">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 <span data-ttu-id="1588c-116">Im vorherigen Beispiel können Sie mithilfe der folgenden Anweisung versuchen, von der versiegelten Klasse zu erben:</span><span class="sxs-lookup"><span data-stu-id="1588c-116">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="1588c-117">Daraus ergibt sich eine Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="1588c-117">The result is an error message:</span></span>  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="1588c-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="1588c-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="1588c-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1588c-119">Remarks</span></span>  
 <span data-ttu-id="1588c-120">Sie sollten generell die folgenden zwei Punkte in Betracht ziehen, um festzustellen, ob Sie eine Klasse, Methode oder Eigenschaft versiegeln sollten:</span><span class="sxs-lookup"><span data-stu-id="1588c-120">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="1588c-121">Die potentiellen Vorteile, die ableitende Klassen durch die Möglichkeit, Ihre Klasse anzupassen, erhalten könnten</span><span class="sxs-lookup"><span data-stu-id="1588c-121">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="1588c-122">Die Möglichkeit, dass ableitende Klassen Ihre Klassen so ändern könnten, dass sie nicht mehr korrekt oder wie erwartet funktionieren</span><span class="sxs-lookup"><span data-stu-id="1588c-122">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1588c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1588c-123">See Also</span></span>  
 [<span data-ttu-id="1588c-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1588c-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1588c-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1588c-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1588c-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1588c-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1588c-127">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="1588c-127">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="1588c-128">Abstrakte und versiegelte Klassen und Klassenmember</span><span class="sxs-lookup"><span data-stu-id="1588c-128">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="1588c-129">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="1588c-129">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="1588c-130">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="1588c-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="1588c-131">override</span><span class="sxs-lookup"><span data-stu-id="1588c-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="1588c-132">virtual</span><span class="sxs-lookup"><span data-stu-id="1588c-132">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)
