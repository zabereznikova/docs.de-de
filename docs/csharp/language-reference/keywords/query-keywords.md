---
title: Abfrageschlüsselwörter – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 01134eda540c5141afbd11b2c89ff779da495a9a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173522"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="6dad1-102">Abfrageschlüsselwörter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6dad1-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="6dad1-103">Dieser Abschnitt enthält die kontextabhängigen Schlüsselwörter, die in Abfrageausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6dad1-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6dad1-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6dad1-104">In this section</span></span>

|<span data-ttu-id="6dad1-105">Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-105">Clause</span></span>|<span data-ttu-id="6dad1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6dad1-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="6dad1-107">from</span><span class="sxs-lookup"><span data-stu-id="6dad1-107">from</span></span>](from-clause.md)|<span data-ttu-id="6dad1-108">Gibt eine Datenquelle und eine Bereichsvariable (ähnlich einer Iterationsvariable) an</span><span class="sxs-lookup"><span data-stu-id="6dad1-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="6dad1-109">where</span><span class="sxs-lookup"><span data-stu-id="6dad1-109">where</span></span>](where-clause.md)|<span data-ttu-id="6dad1-110">Filtert Quellelemente basierend auf einem oder mehreren boolschen Ausdrücken, die durch logische AND- und OR-Operatoren (`&&` oder <code>&#124;&#124;</code>) getrennt sind</span><span class="sxs-lookup"><span data-stu-id="6dad1-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="6dad1-111">select</span><span class="sxs-lookup"><span data-stu-id="6dad1-111">select</span></span>](select-clause.md)|<span data-ttu-id="6dad1-112">Gibt den Typ und die Form an, über die die Elemente in der zurückgegebenen Sequenz verfügen werden, wenn die Abfrage ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="6dad1-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="6dad1-113">group</span><span class="sxs-lookup"><span data-stu-id="6dad1-113">group</span></span>](group-clause.md)|<span data-ttu-id="6dad1-114">Gruppiert Abfrageergebnisse entsprechend eines angegebenen Schlüsselwerts</span><span class="sxs-lookup"><span data-stu-id="6dad1-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="6dad1-115">into</span><span class="sxs-lookup"><span data-stu-id="6dad1-115">into</span></span>](into.md)|<span data-ttu-id="6dad1-116">Stellt einen Bezeichner bereit, der als Verweis auf die Ergebnisse einer join-, group- oder select-Klausel dienen kann</span><span class="sxs-lookup"><span data-stu-id="6dad1-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="6dad1-117">orderby</span><span class="sxs-lookup"><span data-stu-id="6dad1-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="6dad1-118">Sortiert Abfrageergebnisse in aufsteigender oder absteigender Reihenfolge, basierend auf der Standardvergleichsfunktion für den Elementtyp</span><span class="sxs-lookup"><span data-stu-id="6dad1-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="6dad1-119">join</span><span class="sxs-lookup"><span data-stu-id="6dad1-119">join</span></span>](join-clause.md)|<span data-ttu-id="6dad1-120">Verknüpft zwei Datenquellen basierend auf einem Gleichheitsvergleich zwischen zwei angegebenen übereinstimmenden Kriterien</span><span class="sxs-lookup"><span data-stu-id="6dad1-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="6dad1-121">let</span><span class="sxs-lookup"><span data-stu-id="6dad1-121">let</span></span>](let-clause.md)|<span data-ttu-id="6dad1-122">Führt eine Bereichsvariable zum Speichern von Unterausdruckergebnissen in einem Abfrageausdruck ein</span><span class="sxs-lookup"><span data-stu-id="6dad1-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="6dad1-123">in</span><span class="sxs-lookup"><span data-stu-id="6dad1-123">in</span></span>](in.md)|<span data-ttu-id="6dad1-124">Kontextabhängiges Schlüsselwort in einer [join](join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6dad1-125">on</span><span class="sxs-lookup"><span data-stu-id="6dad1-125">on</span></span>](on.md)|<span data-ttu-id="6dad1-126">Kontextabhängiges Schlüsselwort in einer [join](join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6dad1-127">equals</span><span class="sxs-lookup"><span data-stu-id="6dad1-127">equals</span></span>](equals.md)|<span data-ttu-id="6dad1-128">Kontextabhängiges Schlüsselwort in einer [join](join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6dad1-129">by</span><span class="sxs-lookup"><span data-stu-id="6dad1-129">by</span></span>](by.md)|<span data-ttu-id="6dad1-130">Kontextabhängiges Schlüsselwort in einer [group](group-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="6dad1-131">ascending</span><span class="sxs-lookup"><span data-stu-id="6dad1-131">ascending</span></span>](ascending.md)|<span data-ttu-id="6dad1-132">Kontextabhängiges Schlüsselwort in einer [orderby](orderby-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="6dad1-133">descending</span><span class="sxs-lookup"><span data-stu-id="6dad1-133">descending</span></span>](descending.md)|<span data-ttu-id="6dad1-134">Kontextabhängiges Schlüsselwort in einer [orderby](orderby-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="6dad1-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6dad1-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6dad1-135">See also</span></span>

- [<span data-ttu-id="6dad1-136">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6dad1-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6dad1-137">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="6dad1-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6dad1-138">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="6dad1-138">LINQ in C#</span></span>](../../linq/index.md)
