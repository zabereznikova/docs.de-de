---
description: into – C#-Referenz
title: into – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 4712a6906195c5d8bc09c7b734dba0df4d2b08c8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89134522"
---
# <a name="into-c-reference"></a><span data-ttu-id="ade60-103">into (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ade60-103">into (C# Reference)</span></span>

<span data-ttu-id="ade60-104">Das Kontextschlüsselwort `into` kann zum Erstellen eines temporären Bezeichners verwendet werden, der die Ergebnisse einer [group](group-clause.md)-, [join](join-clause.md)- oder [select](select-clause.md)-Klausel in einem neuen Bezeichner speichert.</span><span class="sxs-lookup"><span data-stu-id="ade60-104">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="ade60-105">Dieser Bezeichner kann wiederum ein Generator für zusätzliche Abfragebefehle sein.</span><span class="sxs-lookup"><span data-stu-id="ade60-105">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="ade60-106">In einer `group`- oder `select`-Klausel wird die Verwendung des neuen Bezeichners auch als *Fortsetzung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ade60-106">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="ade60-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ade60-107">Example</span></span>

<span data-ttu-id="ade60-108">Das folgende Beispiel zeigt die Verwendung des Schlüsselworts `into` zur Aktivierung eines temporären Bezeichners `fruitGroup`, der über einen abgeleiteten Typ `IGrouping` verfügt.</span><span class="sxs-lookup"><span data-stu-id="ade60-108">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="ade60-109">Mit diesem Bezeichner können Sie die <xref:System.Linq.Enumerable.Count%2A>-Methode für jede Gruppe aufrufen und nur die Gruppen auswählen, die mindestens zwei Wörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="ade60-109">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="ade60-110">Die Verwendung von `into` in einer `group`-Klausel ist nur erforderlich, wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ade60-110">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="ade60-111">Weitere Informationen finden Sie unter [group-Klausel](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ade60-111">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="ade60-112">Ein Beispiel für die Verwendung von `into` in einer `join`-Klausel finden Sie unter [join-Klausel](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ade60-112">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ade60-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ade60-113">See also</span></span>

- [<span data-ttu-id="ade60-114">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ade60-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="ade60-115">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="ade60-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="ade60-116">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="ade60-116">group clause</span></span>](group-clause.md)
