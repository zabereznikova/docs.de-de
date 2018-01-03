---
title: NULL-Semantik
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6786c7ea4441b1a753d6f0b4213f40fa64dcb4ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="null-semantics"></a><span data-ttu-id="79d7d-102">NULL-Semantik</span><span class="sxs-lookup"><span data-stu-id="79d7d-102">Null Semantics</span></span>
<span data-ttu-id="79d7d-103">Die folgende Tabelle enthält Links zu verschiedenen Teilen der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Dokumentation, in denen es um `null` -Probleme geht (bzw. um`Nothing` -Probleme in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="79d7d-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) issues are discussed.</span></span>  
  
|<span data-ttu-id="79d7d-104">Thema</span><span class="sxs-lookup"><span data-stu-id="79d7d-104">Topic</span></span>|<span data-ttu-id="79d7d-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79d7d-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="79d7d-106">SQL-CLR-Typenkonflikte</span><span class="sxs-lookup"><span data-stu-id="79d7d-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="79d7d-107">Der Abschnitt "NULL-Semantik" dieses Themas umfasst Informationen zum dreistufigen SQL-Boolean und zum zweistufigen Common Language Runtime (CLR)- <xref:System.Boolean>, zum `Nothing` -Literal ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) und zum `null` -Literal (C#) sowie zu ähnliche Aspekten.</span><span class="sxs-lookup"><span data-stu-id="79d7d-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="79d7d-108">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="79d7d-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="79d7d-109">Im Abschnitt "NULL-Semantik" dieses Themas wird die NULL-Vergleichssemantik in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79d7d-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="79d7d-110">System.String-Methoden</span><span class="sxs-lookup"><span data-stu-id="79d7d-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="79d7d-111">Der Abschnitt "Unterschiede zu .NET" dieses Themas erläutert, warum der Rückgabewert 0 von <xref:System.String.LastIndexOf%2A> auf eine NULL-Zeichenfolge oder auf die gefundene Position 0 hinweisen kann.</span><span class="sxs-lookup"><span data-stu-id="79d7d-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="79d7d-112">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="79d7d-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="79d7d-113">Erläutert, wie der <xref:System.Linq.Enumerable.Sum%2A> -Operator bei einer Sequenz, die nur aus Nullen besteht, bzw. bei einer leeren Sequenz zu `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) und nicht zu 0 führt.</span><span class="sxs-lookup"><span data-stu-id="79d7d-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79d7d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79d7d-114">See Also</span></span>  
 [<span data-ttu-id="79d7d-115">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="79d7d-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
