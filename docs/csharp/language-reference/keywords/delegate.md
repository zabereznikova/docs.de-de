---
title: Delegat (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="delegate-c-reference"></a><span data-ttu-id="37dc9-102">Delegat (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="37dc9-102">delegate (C# Reference)</span></span>
<span data-ttu-id="37dc9-103">Die Deklaration eines Delegattyps ähnelt einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="37dc9-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="37dc9-104">Er verfügt über einen Rückgabewert und eine beliebige Anzahl Parameter eines beliebigen Typs:</span><span class="sxs-lookup"><span data-stu-id="37dc9-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="37dc9-105">Ein `delegate` ist ein Verweistyp, der verwendet werden kann, um eine benannte oder anonyme Methode zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="37dc9-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="37dc9-106">Delegaten entsprechen den Funktionszeigern in C++, sind jedoch typsicher und geschützt.</span><span class="sxs-lookup"><span data-stu-id="37dc9-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="37dc9-107">Anwendungsmöglichkeiten von Delegaten finden Sie unter [Delegaten](../../../csharp/programming-guide/delegates/index.md) und [Generische Delegaten](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="37dc9-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37dc9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37dc9-108">Remarks</span></span>  
 <span data-ttu-id="37dc9-109">Delegaten bilden die Grundlage für [Ereignisse](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="37dc9-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="37dc9-110">Ein Delegat kann instanziiert werden, entweder durch Zuordnen mit einer benannten oder einer anonymen Methode.</span><span class="sxs-lookup"><span data-stu-id="37dc9-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="37dc9-111">Weitere Informationen finden Sie unter [Benannte Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) und [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="37dc9-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="37dc9-112">Der Delegat muss mit einer Methode oder einem Lambda-Ausdruck instanziiert werden, der über einen kompatiblen Rückgabetypen und Eingabeparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="37dc9-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="37dc9-113">Weitere Informationen zum Grad der Varianz, der in der Methodensignatur zulässig ist, finden Sie unter [Varianz bei Delegaten](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span><span class="sxs-lookup"><span data-stu-id="37dc9-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span></span> <span data-ttu-id="37dc9-114">Für die Verwendung mit anonymen Methoden werden der Delegat und der Code, der mit ihm zugeordnet werden soll, zusammen deklariert.</span><span class="sxs-lookup"><span data-stu-id="37dc9-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="37dc9-115">Beide Methoden zur Instanziierung von Delegaten werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="37dc9-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37dc9-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37dc9-116">Example</span></span>  
 <span data-ttu-id="37dc9-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="37dc9-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="37dc9-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="37dc9-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37dc9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37dc9-119">See Also</span></span>  
 <span data-ttu-id="37dc9-120">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="37dc9-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="37dc9-122">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="37dc9-123">[Verweistypen](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-123">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="37dc9-124">[Delegaten](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-124">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="37dc9-125">[Ereignisse](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-125">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="37dc9-126">[Delegate mit benannten im Vergleich zu Anonyme Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="37dc9-126">[Delegates with Named vs. Anonymous Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span></span>  
 [<span data-ttu-id="37dc9-127">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="37dc9-127">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

