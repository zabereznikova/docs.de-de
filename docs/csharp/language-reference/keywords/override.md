---
title: override (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
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
ms.openlocfilehash: 0f5a87eaa5894b61187c379c92ad785336aa79b2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="override-c-reference"></a><span data-ttu-id="abf90-102">override (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="abf90-102">override (C# Reference)</span></span>
<span data-ttu-id="abf90-103">Der `override`-Modifizierer wird benötigt, um die abstrakte oder virtuelle Implementierung einer geerbten Methode, Eigenschaft, eines Indexers oder Ereignisses zu erweitern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="abf90-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abf90-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abf90-104">Example</span></span>  
 <span data-ttu-id="abf90-105">In diesem Beispiel muss die `Square`-Klasse eine überschriebene Implementierung von `Area` bereitstellen, da `Area` von der abstrakten `ShapesClass` geerbt wurde:</span><span class="sxs-lookup"><span data-stu-id="abf90-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 <span data-ttu-id="abf90-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abf90-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span></span>  
  
 <span data-ttu-id="abf90-107">Eine `override`-Methode stellt eine neue Implementierung eines Members bereit, der von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="abf90-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="abf90-108">Die Methode, die durch eine `override`-Deklaration überschrieben wird, wird als die überschriebene Basismethode bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="abf90-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="abf90-109">Die überschriebene Basismethode muss die gleiche Signatur wie die `override`-Methode haben.</span><span class="sxs-lookup"><span data-stu-id="abf90-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="abf90-110">Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="abf90-110">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="abf90-111">Sie können keine nicht virtuelle oder statische Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="abf90-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="abf90-112">Die überschriebene Basismethode muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="abf90-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="abf90-113">Ein `override`-Deklaration kann nicht die Erreichbarkeit auf die `virtual` Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="abf90-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="abf90-114">Sowohl die Methode `override` als auch `virtual` müssen den gleichen [Zugriffsebenenmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) besitzen.</span><span class="sxs-lookup"><span data-stu-id="abf90-114">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="abf90-115">Sie können die Modifizierer `new`, `static` oder `virtual` nicht verwenden, um eine `override`-Methode zu ändern.</span><span class="sxs-lookup"><span data-stu-id="abf90-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="abf90-116">Eine überschreibende Eigenschaftsdeklaration muss genau den selben Zugriffsmodifizierertyp und -namen wie die geerbte Eigenschaft angeben, und die überschriebene Eigenschaft muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="abf90-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="abf90-117">Weitere Informationen zur Verwendung des `override`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="abf90-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="abf90-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abf90-118">Example</span></span>  
 <span data-ttu-id="abf90-119">In diesem Beispiel wird eine Basisklasse namens `Employee` und eine abgeleitete Klasse namens `SalesEmployee` definiert.</span><span class="sxs-lookup"><span data-stu-id="abf90-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="abf90-120">Die `SalesEmployee`-Klasse enthält eine zusätzliche Eigenschaft, `salesbonus`, und überschreibt die `CalculatePay`-Methode, um dies zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="abf90-120">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 <span data-ttu-id="abf90-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="abf90-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="abf90-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="abf90-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="abf90-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abf90-123">See Also</span></span>  
 <span data-ttu-id="abf90-124">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="abf90-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="abf90-126">[Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-126">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="abf90-127">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="abf90-128">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-128">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="abf90-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="abf90-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 <span data-ttu-id="abf90-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="abf90-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="abf90-132">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="abf90-132">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)

