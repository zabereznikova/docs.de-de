---
title: NULL-Semantik
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3c4daa5fd37158f1af31f33ba743a56cf76670d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="null-semantics"></a><span data-ttu-id="7cbe9-102">NULL-Semantik</span><span class="sxs-lookup"><span data-stu-id="7cbe9-102">Null Semantics</span></span>
<span data-ttu-id="7cbe9-103">Die folgende Tabelle enthält Links zu verschiedenen Bestandteile der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation, in denen `null` (`Nothing` in Visual Basic) werden Probleme erläutert.</span><span class="sxs-lookup"><span data-stu-id="7cbe9-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="7cbe9-104">Thema</span><span class="sxs-lookup"><span data-stu-id="7cbe9-104">Topic</span></span>|<span data-ttu-id="7cbe9-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cbe9-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7cbe9-106">SQL-CLR-Typenkonflikte</span><span class="sxs-lookup"><span data-stu-id="7cbe9-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="7cbe9-107">Der Abschnitt "Null-Semantik" dieses Themas umfasst Informationen zum dreistufigen SQL-Boolean und die common Language Runtime (CLR) von zwei Status <xref:System.Boolean>, das Literal `Nothing` (Visual Basic) und `null` (c#), sowie zu ähnliche Aspekten.</span><span class="sxs-lookup"><span data-stu-id="7cbe9-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="7cbe9-108">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="7cbe9-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="7cbe9-109">Im Abschnitt "NULL-Semantik" dieses Themas wird die NULL-Vergleichssemantik in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7cbe9-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="7cbe9-110">System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="7cbe9-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="7cbe9-111">Der Abschnitt "Unterschiede zu .NET" dieses Themas erläutert, warum der Rückgabewert 0 von <xref:System.String.LastIndexOf%2A> auf eine NULL-Zeichenfolge oder auf die gefundene Position 0 hinweisen kann.</span><span class="sxs-lookup"><span data-stu-id="7cbe9-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="7cbe9-112">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="7cbe9-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="7cbe9-113">Beschreibt, wie die <xref:System.Linq.Enumerable.Sum%2A> Operator ergibt `null` (`Nothing` in Visual Basic) anstelle von 0 für eine Sequenz, die nur NULL-Werte enthält oder eine leere Sequenz.</span><span class="sxs-lookup"><span data-stu-id="7cbe9-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7cbe9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cbe9-114">See Also</span></span>  
 [<span data-ttu-id="7cbe9-115">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="7cbe9-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
