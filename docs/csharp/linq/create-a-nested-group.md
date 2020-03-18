---
title: Erstellen einer geschachtelten Gruppe (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie eine geschachtelten Gruppe in einem LINQ-Abfrageausdruck in C# erstellen.
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688617"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="76e03-103">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="76e03-103">Create a nested group</span></span>

<span data-ttu-id="76e03-104">Im folgenden Beispiel wird veranschaulicht, wie geschachtelte Gruppen in einem LINQ-Abfrageausdruck erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="76e03-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="76e03-105">Jede Gruppe, die nach Studienjahr oder Klassenstufe erstellt wird, wird basierend auf den Namen der einzelnen Personen weiter in Gruppen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="76e03-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>

## <a name="example"></a><span data-ttu-id="76e03-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76e03-106">Example</span></span>

> [!NOTE]
> <span data-ttu-id="76e03-107">Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="76e03-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

<span data-ttu-id="76e03-108">Beachten Sie, das drei geschachtelte `foreach`-Schleifen für die Iteration über die inneren Elemente einer geschachtelten Gruppe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="76e03-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>

## <a name="see-also"></a><span data-ttu-id="76e03-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76e03-109">See also</span></span>

- [<span data-ttu-id="76e03-110">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="76e03-110">Language Integrated Query (LINQ)</span></span>](index.md)
