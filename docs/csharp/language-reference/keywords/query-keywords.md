---
title: "Abfrageschlüsselwörter (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
caps.latest.revision: 15
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
ms.openlocfilehash: 6dadce6d48e711032cca03a7f7c2ba02360e685f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="0dfa3-102">Abfrageschlüsselwörter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0dfa3-102">Query Keywords (C# Reference)</span></span>
<span data-ttu-id="0dfa3-103">Dieser Abschnitt enthält die kontextabhängigen Schlüsselwörter, die in Abfrageausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0dfa3-103">This section contains the contextual keywords used in query expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dfa3-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0dfa3-104">In This Section</span></span>  
  
|<span data-ttu-id="0dfa3-105">Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-105">Clause</span></span>|<span data-ttu-id="0dfa3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0dfa3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0dfa3-107">from</span><span class="sxs-lookup"><span data-stu-id="0dfa3-107">from</span></span>](../../../csharp/language-reference/keywords/from-clause.md)|<span data-ttu-id="0dfa3-108">Gibt eine Datenquelle und eine Bereichsvariable (ähnlich einer Iterationsvariable) an</span><span class="sxs-lookup"><span data-stu-id="0dfa3-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|  
|[<span data-ttu-id="0dfa3-109">where</span><span class="sxs-lookup"><span data-stu-id="0dfa3-109">where</span></span>](../../../csharp/language-reference/keywords/where-clause.md)|<span data-ttu-id="0dfa3-110">Filtert Quellelemente basierend auf einem oder mehreren boolschen Ausdrücken, die durch logische AND- und OR-Operatoren (`&&` oder <code>&#124;&#124;</code>) getrennt sind</span><span class="sxs-lookup"><span data-stu-id="0dfa3-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|  
|[<span data-ttu-id="0dfa3-111">select</span><span class="sxs-lookup"><span data-stu-id="0dfa3-111">select</span></span>](../../../csharp/language-reference/keywords/select-clause.md)|<span data-ttu-id="0dfa3-112">Gibt den Typ und die Form an, über die die Elemente in der zurückgegebenen Sequenz verfügen werden, wenn die Abfrage ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0dfa3-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|  
|[<span data-ttu-id="0dfa3-113">group</span><span class="sxs-lookup"><span data-stu-id="0dfa3-113">group</span></span>](../../../csharp/language-reference/keywords/group-clause.md)|<span data-ttu-id="0dfa3-114">Gruppiert Abfrageergebnisse entsprechend eines angegebenen Schlüsselwerts</span><span class="sxs-lookup"><span data-stu-id="0dfa3-114">Groups query results according to a specified key value.</span></span>|  
|[<span data-ttu-id="0dfa3-115">into</span><span class="sxs-lookup"><span data-stu-id="0dfa3-115">into</span></span>](../../../csharp/language-reference/keywords/into.md)|<span data-ttu-id="0dfa3-116">Stellt einen Bezeichner bereit, der als Verweis auf die Ergebnisse einer join-, group- oder select-Klausel dienen kann</span><span class="sxs-lookup"><span data-stu-id="0dfa3-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|  
|[<span data-ttu-id="0dfa3-117">orderby</span><span class="sxs-lookup"><span data-stu-id="0dfa3-117">orderby</span></span>](../../../csharp/language-reference/keywords/orderby-clause.md)|<span data-ttu-id="0dfa3-118">Sortiert Abfrageergebnisse in aufsteigender oder absteigender Reihenfolge, basierend auf der Standardvergleichsfunktion für den Elementtyp</span><span class="sxs-lookup"><span data-stu-id="0dfa3-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|  
|[<span data-ttu-id="0dfa3-119">join</span><span class="sxs-lookup"><span data-stu-id="0dfa3-119">join</span></span>](../../../csharp/language-reference/keywords/join-clause.md)|<span data-ttu-id="0dfa3-120">Verknüpft zwei Datenquellen basierend auf einem Gleichheitsvergleich zwischen zwei angegebenen übereinstimmenden Kriterien</span><span class="sxs-lookup"><span data-stu-id="0dfa3-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|  
|[<span data-ttu-id="0dfa3-121">let</span><span class="sxs-lookup"><span data-stu-id="0dfa3-121">let</span></span>](../../../csharp/language-reference/keywords/let-clause.md)|<span data-ttu-id="0dfa3-122">Führt eine Bereichsvariable zum Speichern von Unterausdruckergebnissen in einem Abfrageausdruck ein</span><span class="sxs-lookup"><span data-stu-id="0dfa3-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|  
|[<span data-ttu-id="0dfa3-123">in</span><span class="sxs-lookup"><span data-stu-id="0dfa3-123">in</span></span>](../../../csharp/language-reference/keywords/in.md)|<span data-ttu-id="0dfa3-124">Kontextabhängiges Schlüsselwort in einer [join](../../../csharp/language-reference/keywords/join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-124">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0dfa3-125">on</span><span class="sxs-lookup"><span data-stu-id="0dfa3-125">on</span></span>](../../../csharp/language-reference/keywords/on.md)|<span data-ttu-id="0dfa3-126">Kontextabhängiges Schlüsselwort in einer [join](../../../csharp/language-reference/keywords/join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-126">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0dfa3-127">equals</span><span class="sxs-lookup"><span data-stu-id="0dfa3-127">equals</span></span>](../../../csharp/language-reference/keywords/equals.md)|<span data-ttu-id="0dfa3-128">Kontextabhängiges Schlüsselwort in einer [join](../../../csharp/language-reference/keywords/join-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-128">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0dfa3-129">by</span><span class="sxs-lookup"><span data-stu-id="0dfa3-129">by</span></span>](../../../csharp/language-reference/keywords/by.md)|<span data-ttu-id="0dfa3-130">Kontextabhängiges Schlüsselwort in einer [group](../../../csharp/language-reference/keywords/group-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-130">Contextual keyword in a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0dfa3-131">ascending</span><span class="sxs-lookup"><span data-stu-id="0dfa3-131">ascending</span></span>](../../../csharp/language-reference/keywords/ascending.md)|<span data-ttu-id="0dfa3-132">Kontextabhängiges Schlüsselwort in einer [orderby](../../../csharp/language-reference/keywords/orderby-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-132">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
|[<span data-ttu-id="0dfa3-133">descending</span><span class="sxs-lookup"><span data-stu-id="0dfa3-133">descending</span></span>](../../../csharp/language-reference/keywords/descending.md)|<span data-ttu-id="0dfa3-134">Kontextabhängiges Schlüsselwort in einer [orderby](../../../csharp/language-reference/keywords/orderby-clause.md)-Klausel</span><span class="sxs-lookup"><span data-stu-id="0dfa3-134">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0dfa3-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dfa3-135">See Also</span></span>  
 <span data-ttu-id="0dfa3-136">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0dfa3-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0dfa3-137">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="0dfa3-137">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="0dfa3-138">[LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="0dfa3-138">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="0dfa3-139">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="0dfa3-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

