---
title: protected (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: a3115fe82b452f52ee75cf222302ece0fc67b330
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="protected-c-reference"></a><span data-ttu-id="0a620-102">protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0a620-102">protected (C# Reference)</span></span>
<span data-ttu-id="0a620-103">Das `protected`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="0a620-103">The `protected` keyword is a member access modifier.</span></span> 

 > <span data-ttu-id="0a620-104">Auf dieser Seite wird der Zugriff auf `protected` behandelt.</span><span class="sxs-lookup"><span data-stu-id="0a620-104">This page covers `protected` access.</span></span> <span data-ttu-id="0a620-105">Das Schlüsselwort `protected` ist auch Teil der Zugriffsmodifizierer [`protected internal`](./protected-internal.md) und [`private protected`](./private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="0a620-105">The `protected` keyword is also part of the [`protected internal`](./protected-internal.md) and [`private protected`](./private-protected.md) access modifiers.</span></span> 

<span data-ttu-id="0a620-106">Auf einen geschützten Member kann innerhalb seiner Klasse und von Instanzen abgeleiteter Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0a620-106">A protected member is accessible within its class and by derived class instances.</span></span> 

<span data-ttu-id="0a620-107">Einen Vergleich von `protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0a620-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
  
## <a name="example"></a><span data-ttu-id="0a620-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a620-108">Example</span></span>  
 <span data-ttu-id="0a620-109">Auf einen geschützten Member einer Basisklasse kann in einer abgeleiteten Klasse zugegriffen werden, nur wenn der Zugriff über den Typ der abgeleiteten Klasse erfolgt.</span><span class="sxs-lookup"><span data-stu-id="0a620-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="0a620-110">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="0a620-110">For example, consider the following code segment:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 <span data-ttu-id="0a620-111">Die Anweisung `a.x = 10` generiert einen Fehler, da sie innerhalb der statischen Main-Methode erstellt wird und keine Instanz der Klasse B ist.</span><span class="sxs-lookup"><span data-stu-id="0a620-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>  
  
 <span data-ttu-id="0a620-112">Strukturmember können nicht geschützt werden, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a620-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a620-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a620-113">Example</span></span>  
 <span data-ttu-id="0a620-114">In diesem Beispiel wird die `DerivedPoint`-Klasse von `Point` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0a620-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="0a620-115">Daher können Sie direkt von der abgeleiteten Klasse auf die geschützten Member der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0a620-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 <span data-ttu-id="0a620-116">Wenn Sie die Zugriffsebenen von `x` und `y` auf [private](../../../csharp/language-reference/keywords/private.md) ändern, wird der Compiler die Fehlermeldungen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="0a620-116">If you change the access levels of `x` and `y` to [private](../../../csharp/language-reference/keywords/private.md), the compiler will issue the error messages:</span></span>  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="0a620-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0a620-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a620-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a620-118">See Also</span></span>  
 [<span data-ttu-id="0a620-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0a620-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0a620-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0a620-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0a620-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0a620-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0a620-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="0a620-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="0a620-123">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="0a620-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="0a620-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0a620-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="0a620-125">public</span><span class="sxs-lookup"><span data-stu-id="0a620-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="0a620-126">private</span><span class="sxs-lookup"><span data-stu-id="0a620-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="0a620-127">internal</span><span class="sxs-lookup"><span data-stu-id="0a620-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="0a620-128">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="0a620-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>