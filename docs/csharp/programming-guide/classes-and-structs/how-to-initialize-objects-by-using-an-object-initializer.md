---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie Objektinitialisierer verwenden, um Typobjekte in C# zu initialisieren, ohne einen Konstruktor aufzurufen. Verwenden Sie einen Objektinitialisierer, um einen anonymen Typ zu definieren.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0c2d38713a1fdefd922234a02e23518c0f00add5
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512781"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="31b58-104">Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="31b58-104">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="31b58-105">Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="31b58-105">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="31b58-106">Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31b58-106">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="31b58-107">Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den parameterlosen Instanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="31b58-107">The compiler processes object initializers by first accessing the parameterless instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="31b58-108">Daher tritt bei Objektinitialisierern, die öffentlichen Zugriff benötigen, ein Fehler auf, wenn der parameterlose Konstruktor in der Klasse als `private` deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="31b58-108">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="31b58-109">Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="31b58-109">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="31b58-110">Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="31b58-110">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31b58-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31b58-111">Example</span></span>  

<span data-ttu-id="31b58-112">Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="31b58-112">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="31b58-113">Dieses Beispiel legt Eigenschaften für den Typ `StudentName` fest:</span><span class="sxs-lookup"><span data-stu-id="31b58-113">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="31b58-114">Objektinitialisierer können dafür verwendet werden, Indexer in einem Objekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="31b58-114">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="31b58-115">Das folgende Beispiel definiert eine `BaseballTeam`-Klasse, die einen Indexer verwendet, um Player an verschiedenen Positionen abzurufen und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="31b58-115">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="31b58-116">Der Initialisierer kann Player auf Grundlage der Abkürzung für die Position oder der Zahl, die für jede einzelne Position auf einem Baseball-Scoresheet verwendet wird, zuweisen:</span><span class="sxs-lookup"><span data-stu-id="31b58-116">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="31b58-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31b58-117">See also</span></span>

- [<span data-ttu-id="31b58-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="31b58-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="31b58-119">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="31b58-119">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
