---
title: C#-Delegaten – Überblick über C#
description: Hier lernen Sie späte Bindungen mit C#-Delegaten kennen.
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159168"
---
# <a name="delegates"></a><span data-ttu-id="d7192-103">Delegaten</span><span class="sxs-lookup"><span data-stu-id="d7192-103">Delegates</span></span>

<span data-ttu-id="d7192-104">Ein ***Delegattyp*** stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar.</span><span class="sxs-lookup"><span data-stu-id="d7192-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="d7192-105">Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d7192-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="d7192-106">Delegaten ähneln konzeptionell Funktionszeigern, die es in einigen anderen Sprachen gibt.</span><span class="sxs-lookup"><span data-stu-id="d7192-106">Delegates are similar to the concept of function pointers found in some other languages.</span></span> <span data-ttu-id="d7192-107">Im Gegensatz zu Funktionszeigern sind Delegaten objektorientiert und typsicher.</span><span class="sxs-lookup"><span data-stu-id="d7192-107">Unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="d7192-108">Im folgenden Beispiel wird ein Delegattyp namens `Function` deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7192-108">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="d7192-109">Eine Instanz des Delegattyps `Function` kann auf jede Methode verweisen, die ein `double`-Argument und einen `double`-Wert akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d7192-109">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="d7192-110">Die `Apply`-Methode wendet eine bestimmte Funktion auf die Elemente eines `double[]` an, wobei ein `double[]` mit den Ergebnissen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7192-110">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="d7192-111">In der `Main`-Methode wird `Apply` verwendet, um drei verschiedene Funktionen auf ein `double[]` anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d7192-111">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="d7192-112">Ein Delegat kann entweder auf eine statische Methode verweisen (z.B. `Square` oder `Math.Sin` im vorherigen Beispiel) oder eine Instanzmethode (z.B. `m.Multiply` im vorherigen Beispiel).</span><span class="sxs-lookup"><span data-stu-id="d7192-112">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="d7192-113">Ein Delegat, der auf eine Instanzmethode verweist, verweist auch auf ein bestimmtes Objekt, und wenn die Instanzmethode durch den Delegaten aufgerufen wird, wird das Objekt `this` im Aufruf.</span><span class="sxs-lookup"><span data-stu-id="d7192-113">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="d7192-114">Delegaten können auch mithilfe anonymer Funktionen erstellt werden, bei denen es sich um „Inlinemethoden“ handelt, die bei der Deklaration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d7192-114">Delegates can also be created using anonymous functions, which are "inline methods" that are created when declared.</span></span> <span data-ttu-id="d7192-115">Anonyme Funktionen können die lokalen Variablen der umgebenden Methoden sehen.</span><span class="sxs-lookup"><span data-stu-id="d7192-115">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="d7192-116">Im folgenden Beispiel wird keine Klasse erstellt:</span><span class="sxs-lookup"><span data-stu-id="d7192-116">The following example doesn't create a class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="d7192-117">Ein Delegat weiß nicht und interessiert sich nicht dafür, welche Klasse der Methode er referenziert. Wichtig ist nur, dass die referenzierte Methode über dieselben Parameter und denselben Rückgabetyp wie der Delegat verfügt.</span><span class="sxs-lookup"><span data-stu-id="d7192-117">A delegate doesn't know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d7192-118">[Zurück](interfaces.md)
>[Weiter](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="d7192-118">[Previous](interfaces.md)
[Next](attributes.md)</span></span>
