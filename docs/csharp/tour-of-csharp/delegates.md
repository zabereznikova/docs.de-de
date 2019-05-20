---
title: C#-Delegaten – Überblick über C#
description: Hier lernen Sie späte Bindungen mit C#-Delegaten kennen.
ms.date: 08/10/2016
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: 35a1e212b50e77eb43271a657c8abb21eb6cfb4a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634632"
---
# <a name="delegates"></a><span data-ttu-id="99deb-103">Delegaten</span><span class="sxs-lookup"><span data-stu-id="99deb-103">Delegates</span></span>

<span data-ttu-id="99deb-104">Ein ***Delegattyp*** stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar.</span><span class="sxs-lookup"><span data-stu-id="99deb-104">A ***delegate type*** represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="99deb-105">Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="99deb-105">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="99deb-106">Delegate ähneln dem Konzept von Funktionszeigern, die Sie in einigen anderen Sprachen finden. Im Gegensatz zu Funktionszeigern sind Delegate allerdings objektorientiert und typsicher.</span><span class="sxs-lookup"><span data-stu-id="99deb-106">Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="99deb-107">Im folgenden Beispiel wird ein Delegattyp namens `Function` deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="99deb-107">The following example declares and uses a delegate type named `Function`.</span></span>

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

<span data-ttu-id="99deb-108">Eine Instanz des Delegattyps `Function` kann auf jede Methode verweisen, die ein `double`-Argument und einen `double`-Wert akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="99deb-108">An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value.</span></span> <span data-ttu-id="99deb-109">Die `Apply`-Methode wendet eine bestimmte Funktion auf die Elemente eines `double[]` an, wobei ein `double[]` mit den Ergebnissen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="99deb-109">The `Apply` method applies a given Function to the elements of a `double[]`, returning a `double[]` with the results.</span></span> <span data-ttu-id="99deb-110">In der `Main`-Methode wird `Apply` verwendet, um drei verschiedene Funktionen auf ein `double[]` anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="99deb-110">In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.</span></span>

<span data-ttu-id="99deb-111">Ein Delegat kann entweder auf eine statische Methode verweisen (z.B. `Square` oder `Math.Sin` im vorherigen Beispiel) oder eine Instanzmethode (z.B. `m.Multiply` im vorherigen Beispiel).</span><span class="sxs-lookup"><span data-stu-id="99deb-111">A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example).</span></span> <span data-ttu-id="99deb-112">Ein Delegat, der auf eine Instanzmethode verweist, verweist auch auf ein bestimmtes Objekt, und wenn die Instanzmethode durch den Delegaten aufgerufen wird, wird das Objekt `this` im Aufruf.</span><span class="sxs-lookup"><span data-stu-id="99deb-112">A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.</span></span>

<span data-ttu-id="99deb-113">Delegaten können auch mit anonymen Funktionen erstellt werden, die dynamisch erstellte „Inlinemethoden“ sind.</span><span class="sxs-lookup"><span data-stu-id="99deb-113">Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly.</span></span> <span data-ttu-id="99deb-114">Anonyme Funktionen können die lokalen Variablen der umgebenden Methoden sehen.</span><span class="sxs-lookup"><span data-stu-id="99deb-114">Anonymous functions can see the local variables of the surrounding methods.</span></span> <span data-ttu-id="99deb-115">Folglich kann das obige Multiplikatorbeispiel ohne Verwendung einer Multiplikatorklasse leichter geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="99deb-115">Thus, the multiplier example above can be written more easily without using a Multiplier class:</span></span>

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

<span data-ttu-id="99deb-116">Eine interessante und nützliche Eigenschaft eines Delegaten ist, dass er die Klasse der Methode, auf die er verweist, nicht kennt oder sie ignoriert; wichtig ist nur, dass die referenzierte Methode die gleichen Parameter und den gleichen Rückgabetyp hat wie der Delegat.</span><span class="sxs-lookup"><span data-stu-id="99deb-116">An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="99deb-117">[Zurück](enums.md)
>[Weiter](attributes.md)</span><span class="sxs-lookup"><span data-stu-id="99deb-117">[Previous](enums.md)
[Next](attributes.md)</span></span>
