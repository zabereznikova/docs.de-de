---
title: Numerische Operatoren und Vergleichsoperatoren
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: b29f78a13d6d0313e0ad29754f6d13ac08be1092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973342"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="3a4d3-102">Numerische Operatoren und Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="3a4d3-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="3a4d3-103">Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="3a4d3-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="3a4d3-104">SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.</span><span class="sxs-lookup"><span data-stu-id="3a4d3-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="3a4d3-105">SQL unterstützt ungeprüfte arithmetische Operatoren nicht.</span><span class="sxs-lookup"><span data-stu-id="3a4d3-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="3a4d3-106">Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3a4d3-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="3a4d3-107">Unterstützte Operatoren</span><span class="sxs-lookup"><span data-stu-id="3a4d3-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3a4d3-108">unterstützt die folgenden Operatoren.</span><span class="sxs-lookup"><span data-stu-id="3a4d3-108">supports the following operators.</span></span>

- <span data-ttu-id="3a4d3-109">Grundlegende arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="3a4d3-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="3a4d3-110">`-` (Subtraktion)</span><span class="sxs-lookup"><span data-stu-id="3a4d3-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="3a4d3-111">Visual Basic-Ganzzahlendivision (`\`)</span><span class="sxs-lookup"><span data-stu-id="3a4d3-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="3a4d3-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="3a4d3-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="3a4d3-113">`-` (unäre Negation)</span><span class="sxs-lookup"><span data-stu-id="3a4d3-113">`-` (unary negation)</span></span>

- <span data-ttu-id="3a4d3-114">Grundlegende Vergleichsoperatoren:</span><span class="sxs-lookup"><span data-stu-id="3a4d3-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="3a4d3-115">Visual Basic `=` und C# `==`</span><span class="sxs-lookup"><span data-stu-id="3a4d3-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="3a4d3-116">Visual Basic `<>` und C# `!=`</span><span class="sxs-lookup"><span data-stu-id="3a4d3-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="3a4d3-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="3a4d3-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="3a4d3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a4d3-118">See also</span></span>

- [<span data-ttu-id="3a4d3-119">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="3a4d3-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [<span data-ttu-id="3a4d3-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="3a4d3-120">C# Operators</span></span>](../../../../../../docs/csharp/language-reference/operators/index.md)
- [<span data-ttu-id="3a4d3-121">Operatoren</span><span class="sxs-lookup"><span data-stu-id="3a4d3-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
