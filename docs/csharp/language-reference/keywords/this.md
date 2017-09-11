---
title: this (C#-Referenz)
description: "Schlüsselwort „this“ (C#-Referenz)"
keywords: "this (C#), Schlüsselwort „this“ (C#), Schlüsselwort „this“ (C#-Referenz), Schlüsselwort „this“ (C#-Programmiersprachenreferenz)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
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
ms.openlocfilehash: 1e764bbd85d06a3b1898f6574064b2844f6d6813
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="this-c-reference"></a><span data-ttu-id="927c5-104">this (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="927c5-104">this (C# Reference)</span></span>
<span data-ttu-id="927c5-105">Das Schlüsselwort `this` verweist auf die aktuelle Instanz der Klasse und wird auch als Modifizierer des ersten Parameters einer Erweiterungsmethode verwendet.</span><span class="sxs-lookup"><span data-stu-id="927c5-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="927c5-106">Dieser Artikel behandelt die Verwendung von `this` mit Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="927c5-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="927c5-107">Weitere Informationen zu seiner Verwendung in Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="927c5-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="927c5-108">Häufige Verwendungen von `this` sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="927c5-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="927c5-109">Zum Qualifizieren von Membern, die durch ähnliche Namen ausgeblendet werden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="927c5-109">To qualify members hidden by similar names, for example:</span></span>  
  
 <span data-ttu-id="927c5-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="927c5-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span></span>  
  
-   <span data-ttu-id="927c5-111">Zum Übergeben eines Objekts als ein Parameter an eine andere Methode, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="927c5-111">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="927c5-112">Zum Deklarieren von Indexern, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="927c5-112">To declare indexers, for example:</span></span>  
  
 <span data-ttu-id="927c5-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="927c5-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span></span>  
  
 <span data-ttu-id="927c5-114">Statische Memberfunktionen haben keinen `this`-Zeiger, da sie auf Klassenebene und nicht als Teil eines Objekts existieren.</span><span class="sxs-lookup"><span data-stu-id="927c5-114">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="927c5-115">Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="927c5-115">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="927c5-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="927c5-116">Example</span></span>  
 <span data-ttu-id="927c5-117">In diesem Beispiel wird `this` verwendet, um die `Employee`-Klassenmember `name` und `alias` zu qualifizieren, die von ähnlichen Namen ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="927c5-117">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="927c5-118">Er wird auch verwendet, um ein Objekt an die Methode `CalcTax` zu übergeben, die zu einer anderen Klasse gehört.</span><span class="sxs-lookup"><span data-stu-id="927c5-118">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 <span data-ttu-id="927c5-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="927c5-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="927c5-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="927c5-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="927c5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="927c5-121">See Also</span></span>  
 <span data-ttu-id="927c5-122">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="927c5-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="927c5-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="927c5-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="927c5-124">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="927c5-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="927c5-125">[base](../../../csharp/language-reference/keywords/base.md) </span><span class="sxs-lookup"><span data-stu-id="927c5-125">[base](../../../csharp/language-reference/keywords/base.md) </span></span>  
 [<span data-ttu-id="927c5-126">Methoden</span><span class="sxs-lookup"><span data-stu-id="927c5-126">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

