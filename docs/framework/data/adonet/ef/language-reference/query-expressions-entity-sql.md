---
title: Abfrageausdrücke (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: ca6b79b4b3d3326a74780345decf58367596adb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175602"
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="81df5-102">Abfrageausdrücke (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="81df5-102">Query Expressions (Entity SQL)</span></span>

<span data-ttu-id="81df5-103">Ein Abfrageausdruck fasst viele verschiedene Abfrageoperatoren in einer einzigen Syntax zusammen.</span><span class="sxs-lookup"><span data-stu-id="81df5-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="81df5-104">stellt verschiedene Arten von Ausdrücken bereit, einschließlich der folgenden: [Literale](literals-entity-sql.md), [Parameter](parameters-entity-sql.md), [Variablen](variables-entity-sql.md), Operatoren, [Funktionen](functions-entity-sql.md), Mengen Operatoren usw.</span><span class="sxs-lookup"><span data-stu-id="81df5-104">provides various kinds of expressions, including the following: [literals](literals-entity-sql.md), [parameters](parameters-entity-sql.md), [variables](variables-entity-sql.md), operators, [functions](functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="81df5-105">Weitere Informationen finden Sie unter [Entity SQL Referenz](entity-sql-reference.md).</span><span class="sxs-lookup"><span data-stu-id="81df5-105">For more information, see [Entity SQL Reference](entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="81df5-106">Klauseln</span><span class="sxs-lookup"><span data-stu-id="81df5-106">Clauses</span></span>  

 <span data-ttu-id="81df5-107">Ein Abfrageausdruck setzt sich aus einer Serie von Klauseln zusammen, die für eine Auflistung von Objekten aufeinander folgende Operationen durchführen.</span><span class="sxs-lookup"><span data-stu-id="81df5-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="81df5-108">Sie basieren auf denselben [Klauseln, die](having-entity-sql.md)in der standardmäßigen SQL-SELECT-Anweisung gefunden werden: [Select](select-entity-sql.md), [from](from-entity-sql.md), [Where](where-entity-sql.md), [Group by](group-by-entity-sql.md), have und [Order by](order-by-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="81df5-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP BY](group-by-entity-sql.md), [HAVING](having-entity-sql.md), and [ORDER BY](order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="81df5-109">`Scope`</span><span class="sxs-lookup"><span data-stu-id="81df5-109">Scope</span></span>  

 <span data-ttu-id="81df5-110">In der FROM-Klausel definierte Namen werden in der Reihenfolge ihres Auftretens (von links nach rechts) in den FROM-Gültigkeitsbereich eingeführt.</span><span class="sxs-lookup"><span data-stu-id="81df5-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="81df5-111">In der JOIN-Liste können Ausdrücke auf Namen verweisen, die zuvor in der Liste definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="81df5-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="81df5-112">Öffentliche Eigenschaften von in der FROM-Klausel festgelegten Elementen werden dem FROM-Gültigkeitsbereich nicht hinzugefügt: Auf sie muss immer mit dem aliasqualifizierten Namen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="81df5-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="81df5-113">Üblicherweise werden im FROM-Gültigkeitsbereich alle Teile des SELECT-Ausdrucks berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="81df5-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81df5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81df5-114">See also</span></span>

- [<span data-ttu-id="81df5-115">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="81df5-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
