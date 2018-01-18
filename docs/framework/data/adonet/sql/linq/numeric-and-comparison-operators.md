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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 56558e790b8aee300da0a75ade7c0ac451a0eca1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="e803b-102">Numerische Operatoren und Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e803b-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="e803b-103">Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="e803b-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="e803b-104">SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.</span><span class="sxs-lookup"><span data-stu-id="e803b-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="e803b-105">SQL unterstützt ungeprüfte arithmetische Operatoren nicht.</span><span class="sxs-lookup"><span data-stu-id="e803b-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="e803b-106">Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e803b-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="e803b-107">Unterstützte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e803b-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e803b-108"> unterstützt die folgenden Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e803b-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="e803b-109">Grundlegende arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="e803b-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="e803b-110">`-` (Subtraktion)</span><span class="sxs-lookup"><span data-stu-id="e803b-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="e803b-111">Visual Basic-Ganzzahlendivision (`\`)</span><span class="sxs-lookup"><span data-stu-id="e803b-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="e803b-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="e803b-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="e803b-113">`-` (unäre Negation)</span><span class="sxs-lookup"><span data-stu-id="e803b-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="e803b-114">Grundlegende Vergleichsoperatoren:</span><span class="sxs-lookup"><span data-stu-id="e803b-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="e803b-115">Visual Basic `=` und C# `==`</span><span class="sxs-lookup"><span data-stu-id="e803b-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="e803b-116">Visual Basic `<>` und C# `!=`</span><span class="sxs-lookup"><span data-stu-id="e803b-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="e803b-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="e803b-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="e803b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e803b-118">See Also</span></span>  
 [<span data-ttu-id="e803b-119">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="e803b-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="e803b-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e803b-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="e803b-121">Operatoren</span><span class="sxs-lookup"><span data-stu-id="e803b-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
