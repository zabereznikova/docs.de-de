---
title: Numerische Operatoren und Vergleichsoperatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0b89555bc71d95291c096d2e694c315720cfb41c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="c8171-102">Numerische Operatoren und Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c8171-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="c8171-103">Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="c8171-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="c8171-104">SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.</span><span class="sxs-lookup"><span data-stu-id="c8171-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="c8171-105">SQL unterstützt ungeprüfte arithmetische Operatoren nicht.</span><span class="sxs-lookup"><span data-stu-id="c8171-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="c8171-106">Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c8171-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="c8171-107">Unterstützte Operatoren</span><span class="sxs-lookup"><span data-stu-id="c8171-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c8171-108"> unterstützt die folgenden Operatoren.</span><span class="sxs-lookup"><span data-stu-id="c8171-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="c8171-109">Grundlegende arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="c8171-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="c8171-110">`-` (Subtraktion)</span><span class="sxs-lookup"><span data-stu-id="c8171-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="c8171-111">Visual Basic-Ganzzahlendivision (`\`)</span><span class="sxs-lookup"><span data-stu-id="c8171-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="c8171-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="c8171-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="c8171-113">`-` (unäre Negation)</span><span class="sxs-lookup"><span data-stu-id="c8171-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="c8171-114">Grundlegende Vergleichsoperatoren:</span><span class="sxs-lookup"><span data-stu-id="c8171-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="c8171-115">Visual Basic `=` und C# `==`</span><span class="sxs-lookup"><span data-stu-id="c8171-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="c8171-116">Visual Basic `<>` und C# `!=`</span><span class="sxs-lookup"><span data-stu-id="c8171-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="c8171-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="c8171-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="c8171-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8171-118">See Also</span></span>  
 [<span data-ttu-id="c8171-119">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="c8171-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="c8171-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c8171-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="c8171-121">Operatoren</span><span class="sxs-lookup"><span data-stu-id="c8171-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
