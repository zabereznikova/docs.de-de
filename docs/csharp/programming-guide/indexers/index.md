---
title: Indexer (C#-Programmierhandbuch)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
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
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="f53c3-102">Indexer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f53c3-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="f53c3-103">Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="f53c3-104">Der indizierte Wert kann festgelegt oder ohne explizite Angabe eines Typs oder Instanzmembers abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="f53c3-105">Indexer ähneln [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md). Der Unterschied besteht jedoch darin, dass ihre Zugriffsmethoden Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="f53c3-106">Im folgenden Beispiel wird eine generische Klasse mit einfachen [get](../../../csharp/language-reference/keywords/get.md)- und [set](../../../csharp/language-reference/keywords/set.md)-Accessormethoden zum Zuweisen und Abrufen von Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="f53c3-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="f53c3-107">Die `Program`-Klasse erstellt eine Instanz dieser Klasse für das Speichern von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="f53c3-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 <span data-ttu-id="f53c3-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f53c3-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f53c3-109">Weitere Beispiele finden Sie unter [Verwandte Abschnitte](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="f53c3-109">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="f53c3-110">Ausdruckstextdefinitionen</span><span class="sxs-lookup"><span data-stu-id="f53c3-110">Expression Body Definitions</span></span>  
 
<span data-ttu-id="f53c3-111">Get- oder Set-Accessoren eines Indexers bestehen häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt oder festlegt.</span><span class="sxs-lookup"><span data-stu-id="f53c3-111">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="f53c3-112">Ausdruckskörpermember bieten eine vereinfachte Syntax zur Unterstützung dieses Szenarios.</span><span class="sxs-lookup"><span data-stu-id="f53c3-112">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="f53c3-113">Ab C# 6 kann ein schreibgeschützter Indexer als Ausdruckskörpermember implementiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f53c3-113">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

<span data-ttu-id="f53c3-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f53c3-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span></span>  

<span data-ttu-id="f53c3-115">Beachten Sie, dass `=>` den Ausdruckstext vorstellt und dass das `get`-Schlüsselwort nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f53c3-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="f53c3-116">Ab C# 7 können der Get- und der Set-Accessor als Ausdruckskörpermember implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-116">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="f53c3-117">In diesem Fall müssen die Schlüsselwörter `get` und `set` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="f53c3-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f53c3-118">For example:</span></span>

<span data-ttu-id="f53c3-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f53c3-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span></span>  
  
## <a name="indexers-overview"></a><span data-ttu-id="f53c3-120">Übersicht über Indexer</span><span class="sxs-lookup"><span data-stu-id="f53c3-120">Indexers Overview</span></span>  
  
-   <span data-ttu-id="f53c3-121">Indexer ermöglichen es Objekten, in ähnlicher Weise wie Arrays indiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-121">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="f53c3-122">Ein `get`-Accessor gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f53c3-122">A `get` accessor returns a value.</span></span> <span data-ttu-id="f53c3-123">Ein `set`-Accessor weist einen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="f53c3-123">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="f53c3-124">Das [this](../../../csharp/language-reference/keywords/this.md)-Schlüsselwort wird zum Definieren des Indexers verwendet.</span><span class="sxs-lookup"><span data-stu-id="f53c3-124">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="f53c3-125">Das [value](../../../csharp/language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Indexer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f53c3-125">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="f53c3-126">Indexer müssen nicht durch einen Ganzzahlwert indiziert werden. Sie können entscheiden, wie Sie den spezifischen Suchmechanismus definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f53c3-126">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="f53c3-127">Indexer können überladen werden.</span><span class="sxs-lookup"><span data-stu-id="f53c3-127">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="f53c3-128">Indexer können mehr als einen formalen Parameter aufweisen, beispielsweise beim Zugreifen auf ein 2D-Array.</span><span class="sxs-lookup"><span data-stu-id="f53c3-128">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <span data-ttu-id="f53c3-129"><a name="BKMK_RelatedSections"></a> Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f53c3-129"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="f53c3-130">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="f53c3-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="f53c3-131">Indexer in Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f53c3-131">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="f53c3-132">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="f53c3-132">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="f53c3-133">Einschränken des Zugriffsmethodenzugriffs</span><span class="sxs-lookup"><span data-stu-id="f53c3-133">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f53c3-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f53c3-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f53c3-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f53c3-135">See Also</span></span>  
 <span data-ttu-id="f53c3-136">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f53c3-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f53c3-137">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f53c3-137">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

