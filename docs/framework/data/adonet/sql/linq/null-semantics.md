---
title: NULL-Semantik
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: eb1e96ba44c5d64e8366a654c2d06d89c9b46c9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172756"
---
# <a name="null-semantics"></a><span data-ttu-id="bb63b-102">NULL-Semantik</span><span class="sxs-lookup"><span data-stu-id="bb63b-102">Null Semantics</span></span>
<span data-ttu-id="bb63b-103">Die folgende Tabelle enthält Links zu verschiedenen Teilen der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation, in denen `null` (`Nothing` in Visual Basic) werden Probleme erläutert.</span><span class="sxs-lookup"><span data-stu-id="bb63b-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="bb63b-104">Thema</span><span class="sxs-lookup"><span data-stu-id="bb63b-104">Topic</span></span>|<span data-ttu-id="bb63b-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb63b-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bb63b-106">SQL-CLR-Typenkonflikte</span><span class="sxs-lookup"><span data-stu-id="bb63b-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="bb63b-107">Im Abschnitt "Null-Semantik" dieses Themas umfasst Informationen zu den drei-Status-SQL-Boolean und die common Language Runtime (CLR) von zwei-Status <xref:System.Boolean>, das Literal `Nothing` (Visual Basic) und `null` (C#), und andere ähnliche Probleme.</span><span class="sxs-lookup"><span data-stu-id="bb63b-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="bb63b-108">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="bb63b-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="bb63b-109">Im Abschnitt "NULL-Semantik" dieses Themas wird die NULL-Vergleichssemantik in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb63b-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="bb63b-110">System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="bb63b-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="bb63b-111">Der Abschnitt "Unterschiede zu .NET" dieses Themas erläutert, warum der Rückgabewert 0 von <xref:System.String.LastIndexOf%2A> auf eine NULL-Zeichenfolge oder auf die gefundene Position 0 hinweisen kann.</span><span class="sxs-lookup"><span data-stu-id="bb63b-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="bb63b-112">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="bb63b-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="bb63b-113">Beschreibt, wie die <xref:System.Linq.Enumerable.Sum%2A> Operator ergibt `null` (`Nothing` in Visual Basic) anstelle von 0 für eine Sequenz, die nur aus Nullen besteht oder eine leere Sequenz.</span><span class="sxs-lookup"><span data-stu-id="bb63b-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb63b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb63b-114">See also</span></span>

- [<span data-ttu-id="bb63b-115">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="bb63b-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
