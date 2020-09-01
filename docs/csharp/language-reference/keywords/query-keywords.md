---
description: Abfrageschlüsselwörter – C#-Referenz
title: Abfrageschlüsselwörter – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 0beea8634d13222aa18f14d79fdbd95a35cc832e
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137135"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="47b12-103">Abfrageschlüsselwörter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="47b12-103">Query keywords (C# Reference)</span></span>

<span data-ttu-id="47b12-104">Dieser Abschnitt enthält die kontextabhängigen Schlüsselwörter, die in Abfrageausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47b12-104">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="47b12-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="47b12-105">In this section</span></span>

|<span data-ttu-id="47b12-106">Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-106">Clause</span></span>|<span data-ttu-id="47b12-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="47b12-107">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="47b12-108">from</span><span class="sxs-lookup"><span data-stu-id="47b12-108">from</span></span>](from-clause.md)|<span data-ttu-id="47b12-109">Gibt eine Datenquelle und eine Bereichsvariable (ähnlich einer Iterationsvariable) an</span><span class="sxs-lookup"><span data-stu-id="47b12-109">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="47b12-110">where</span><span class="sxs-lookup"><span data-stu-id="47b12-110">where</span></span>](where-clause.md)|<span data-ttu-id="47b12-111">Filtert Quellelemente basierend auf einem oder mehreren boolschen Ausdrücken, die durch logische AND- und OR-Operatoren (`&&` oder <code>&#124;&#124;</code>) getrennt sind</span><span class="sxs-lookup"><span data-stu-id="47b12-111">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="47b12-112">select</span><span class="sxs-lookup"><span data-stu-id="47b12-112">select</span></span>](select-clause.md)|<span data-ttu-id="47b12-113">Gibt den Typ und die Form an, über die die Elemente in der zurückgegebenen Sequenz verfügen werden, wenn die Abfrage ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="47b12-113">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="47b12-114">group</span><span class="sxs-lookup"><span data-stu-id="47b12-114">group</span></span>](group-clause.md)|<span data-ttu-id="47b12-115">Gruppiert Abfrageergebnisse entsprechend eines angegebenen Schlüsselwerts</span><span class="sxs-lookup"><span data-stu-id="47b12-115">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="47b12-116">into</span><span class="sxs-lookup"><span data-stu-id="47b12-116">into</span></span>](into.md)|<span data-ttu-id="47b12-117">Stellt einen Bezeichner bereit, der als Verweis auf die Ergebnisse einer join-, group- oder select-Klausel dienen kann</span><span class="sxs-lookup"><span data-stu-id="47b12-117">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="47b12-118">orderby</span><span class="sxs-lookup"><span data-stu-id="47b12-118">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="47b12-119">Sortiert Abfrageergebnisse in aufsteigender oder absteigender Reihenfolge, basierend auf der Standardvergleichsfunktion für den Elementtyp</span><span class="sxs-lookup"><span data-stu-id="47b12-119">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="47b12-120">join</span><span class="sxs-lookup"><span data-stu-id="47b12-120">join</span></span>](join-clause.md)|<span data-ttu-id="47b12-121">Verknüpft zwei Datenquellen basierend auf einem Gleichheitsvergleich zwischen zwei angegebenen übereinstimmenden Kriterien</span><span class="sxs-lookup"><span data-stu-id="47b12-121">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="47b12-122">let</span><span class="sxs-lookup"><span data-stu-id="47b12-122">let</span></span>](let-clause.md)|<span data-ttu-id="47b12-123">Führt eine Bereichsvariable zum Speichern von Unterausdruckergebnissen in einem Abfrageausdruck ein</span><span class="sxs-lookup"><span data-stu-id="47b12-123">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="47b12-124">in</span><span class="sxs-lookup"><span data-stu-id="47b12-124">in</span></span>](in.md)|<span data-ttu-id="47b12-125">Kontextabhängiges Schlüsselwort in einer [join](join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-125">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="47b12-126">on</span><span class="sxs-lookup"><span data-stu-id="47b12-126">on</span></span>](on.md)|<span data-ttu-id="47b12-127">Kontextabhängiges Schlüsselwort in einer [join](join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-127">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="47b12-128">equals</span><span class="sxs-lookup"><span data-stu-id="47b12-128">equals</span></span>](equals.md)|<span data-ttu-id="47b12-129">Kontextabhängiges Schlüsselwort in einer [join](join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-129">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="47b12-130">by</span><span class="sxs-lookup"><span data-stu-id="47b12-130">by</span></span>](by.md)|<span data-ttu-id="47b12-131">Kontextabhängiges Schlüsselwort in einer [group](group-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-131">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="47b12-132">ascending</span><span class="sxs-lookup"><span data-stu-id="47b12-132">ascending</span></span>](ascending.md)|<span data-ttu-id="47b12-133">Kontextabhängiges Schlüsselwort in einer [orderby](orderby-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-133">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="47b12-134">descending</span><span class="sxs-lookup"><span data-stu-id="47b12-134">descending</span></span>](descending.md)|<span data-ttu-id="47b12-135">Kontextabhängiges Schlüsselwort in einer [orderby](orderby-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="47b12-135">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="47b12-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47b12-136">See also</span></span>

- [<span data-ttu-id="47b12-137">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="47b12-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="47b12-138">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="47b12-138">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="47b12-139">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="47b12-139">LINQ in C#</span></span>](../../linq/index.md)
