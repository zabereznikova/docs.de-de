---
title: into – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 4445674c77be397bd6e1d7e385dbd839fbb916aa
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238181"
---
# <a name="into-c-reference"></a><span data-ttu-id="35548-102">into (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="35548-102">into (C# Reference)</span></span>

<span data-ttu-id="35548-103">Das Kontextschlüsselwort `into` kann zum Erstellen eines temporären Bezeichners verwendet werden, der die Ergebnisse einer [group](group-clause.md)-, [join](join-clause.md)- oder [select](select-clause.md)-Klausel in einem neuen Bezeichner speichert.</span><span class="sxs-lookup"><span data-stu-id="35548-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="35548-104">Dieser Bezeichner kann wiederum ein Generator für zusätzliche Abfragebefehle sein.</span><span class="sxs-lookup"><span data-stu-id="35548-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="35548-105">In einer `group`- oder `select`-Klausel wird die Verwendung des neuen Bezeichners auch als *Fortsetzung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="35548-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="35548-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35548-106">Example</span></span>

<span data-ttu-id="35548-107">Das folgende Beispiel zeigt die Verwendung des Schlüsselworts `into` zur Aktivierung eines temporären Bezeichners `fruitGroup`, der über einen abgeleiteten Typ `IGrouping` verfügt.</span><span class="sxs-lookup"><span data-stu-id="35548-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="35548-108">Mit diesem Bezeichner können Sie die <xref:System.Linq.Enumerable.Count%2A>-Methode für jede Gruppe aufrufen und nur die Gruppen auswählen, die mindestens zwei Wörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="35548-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="35548-109">Die Verwendung von `into` in einer `group`-Klausel ist nur erforderlich, wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="35548-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="35548-110">Weitere Informationen finden Sie unter [group-Klausel](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35548-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="35548-111">Ein Beispiel für die Verwendung von `into` in einer `join`-Klausel finden Sie unter [join-Klausel](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35548-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35548-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35548-112">See also</span></span>

- [<span data-ttu-id="35548-113">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="35548-113">Query Keywords (LINQ)</span></span>](query-keywords.md)  
- [<span data-ttu-id="35548-114">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="35548-114">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [<span data-ttu-id="35548-115">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="35548-115">group clause</span></span>](group-clause.md)  