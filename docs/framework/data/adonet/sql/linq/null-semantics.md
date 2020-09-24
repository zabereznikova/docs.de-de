---
title: NULL-Semantik
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 739ee95be45d7d64a4ad1678837b9706a533f07d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147540"
---
# <a name="null-semantics"></a><span data-ttu-id="50763-102">NULL-Semantik</span><span class="sxs-lookup"><span data-stu-id="50763-102">Null Semantics</span></span>

<span data-ttu-id="50763-103">In der folgenden Tabelle finden Sie Links zu verschiedenen Teilen der- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation, `null` in denen ( `Nothing` in Visual Basic) Probleme erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="50763-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="50763-104">Thema</span><span class="sxs-lookup"><span data-stu-id="50763-104">Topic</span></span>|<span data-ttu-id="50763-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50763-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="50763-106">SQL-CLR-Typenkonflikte</span><span class="sxs-lookup"><span data-stu-id="50763-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="50763-107">Der Abschnitt "NULL-Semantik" dieses Themas umfasst die Erörterung des drei-Status-SQL-booleschen Werts im Vergleich zu den zwei-Status-Common Language Runtime (CLR) <xref:System.Boolean> , der Literale `Nothing` (Visual Basic) und `null` (c#) sowie anderer ähnlicher Probleme.</span><span class="sxs-lookup"><span data-stu-id="50763-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="50763-108">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="50763-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="50763-109">Im Abschnitt "NULL-Semantik" dieses Themas wird die NULL-Vergleichssemantik in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50763-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="50763-110">System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="50763-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="50763-111">Der Abschnitt "Unterschiede zu .NET" dieses Themas erläutert, warum der Rückgabewert 0 von <xref:System.String.LastIndexOf%2A> auf eine NULL-Zeichenfolge oder auf die gefundene Position 0 hinweisen kann.</span><span class="sxs-lookup"><span data-stu-id="50763-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="50763-112">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="50763-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="50763-113">Beschreibt, wie der- <xref:System.Linq.Enumerable.Sum%2A> Operator `null` ( `Nothing` in Visual Basic) anstelle von 0 für eine Sequenz ausgewertet wird, die nur Nullen oder eine leere Sequenz enthält.</span><span class="sxs-lookup"><span data-stu-id="50763-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50763-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50763-114">See also</span></span>

- [<span data-ttu-id="50763-115">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="50763-115">Data Types and Functions</span></span>](data-types-and-functions.md)
