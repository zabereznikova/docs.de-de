---
title: this (C#-Referenz)
description: "Schlüsselwort „this“ (C#-Referenz)"
keywords: "this (C#), Schlüsselwort „this“ (C#), Schlüsselwort „this“ (C#-Referenz), Schlüsselwort „this“ (C#-Programmiersprachenreferenz)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords: this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f159967707061481a34e72a97ec8cc8316d982ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="this-c-reference"></a><span data-ttu-id="dc4ef-104">this (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dc4ef-104">this (C# Reference)</span></span>
<span data-ttu-id="dc4ef-105">Das Schlüsselwort `this` verweist auf die aktuelle Instanz der Klasse und wird auch als Modifizierer des ersten Parameters einer Erweiterungsmethode verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc4ef-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc4ef-106">Dieser Artikel behandelt die Verwendung von `this` mit Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="dc4ef-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="dc4ef-107">Weitere Informationen zu seiner Verwendung in Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="dc4ef-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="dc4ef-108">Häufige Verwendungen von `this` sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dc4ef-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="dc4ef-109">Zum Qualifizieren von Membern, die durch ähnliche Namen ausgeblendet werden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="dc4ef-109">To qualify members hidden by similar names, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   <span data-ttu-id="dc4ef-110">Zum Übergeben eines Objekts als ein Parameter an eine andere Methode, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="dc4ef-110">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="dc4ef-111">Zum Deklarieren von Indexern, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="dc4ef-111">To declare indexers, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 <span data-ttu-id="dc4ef-112">Statische Memberfunktionen haben keinen `this`-Zeiger, da sie auf Klassenebene und nicht als Teil eines Objekts existieren.</span><span class="sxs-lookup"><span data-stu-id="dc4ef-112">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="dc4ef-113">Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="dc4ef-113">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc4ef-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc4ef-114">Example</span></span>  
 <span data-ttu-id="dc4ef-115">In diesem Beispiel wird `this` verwendet, um die `Employee`-Klassenmember `name` und `alias` zu qualifizieren, die von ähnlichen Namen ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc4ef-115">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="dc4ef-116">Er wird auch verwendet, um ein Objekt an die Methode `CalcTax` zu übergeben, die zu einer anderen Klasse gehört.</span><span class="sxs-lookup"><span data-stu-id="dc4ef-116">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="dc4ef-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="dc4ef-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc4ef-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc4ef-118">See Also</span></span>  
 [<span data-ttu-id="dc4ef-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dc4ef-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dc4ef-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dc4ef-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dc4ef-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dc4ef-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dc4ef-122">base</span><span class="sxs-lookup"><span data-stu-id="dc4ef-122">base</span></span>](../../../csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="dc4ef-123">Methoden</span><span class="sxs-lookup"><span data-stu-id="dc4ef-123">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
