---
title: Numerische Operatoren und Vergleichsoperatoren
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 7e7af725864aa191f092055fa32b403093321aa5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781295"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="8cc15-102">Numerische Operatoren und Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="8cc15-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="8cc15-103">Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="8cc15-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="8cc15-104">SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.</span><span class="sxs-lookup"><span data-stu-id="8cc15-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="8cc15-105">SQL unterstützt ungeprüfte arithmetische Operatoren nicht.</span><span class="sxs-lookup"><span data-stu-id="8cc15-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="8cc15-106">Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8cc15-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="8cc15-107">Unterstützte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cc15-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8cc15-108">unterstützt die folgenden Operatoren.</span><span class="sxs-lookup"><span data-stu-id="8cc15-108">supports the following operators.</span></span>

- <span data-ttu-id="8cc15-109">Grundlegende arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cc15-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="8cc15-110">`-` (Subtraktion)</span><span class="sxs-lookup"><span data-stu-id="8cc15-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="8cc15-111">Visual Basic-Ganzzahlendivision (`\`)</span><span class="sxs-lookup"><span data-stu-id="8cc15-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="8cc15-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="8cc15-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="8cc15-113">`-` (unäre Negation)</span><span class="sxs-lookup"><span data-stu-id="8cc15-113">`-` (unary negation)</span></span>

- <span data-ttu-id="8cc15-114">Grundlegende Vergleichsoperatoren:</span><span class="sxs-lookup"><span data-stu-id="8cc15-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="8cc15-115">Visual Basic `=` und C# `==`</span><span class="sxs-lookup"><span data-stu-id="8cc15-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="8cc15-116">Visual Basic `<>` und C# `!=`</span><span class="sxs-lookup"><span data-stu-id="8cc15-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="8cc15-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="8cc15-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="8cc15-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cc15-118">See also</span></span>

- [<span data-ttu-id="8cc15-119">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="8cc15-119">Data Types and Functions</span></span>](data-types-and-functions.md)
- [<span data-ttu-id="8cc15-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cc15-120">C# Operators</span></span>](../../../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="8cc15-121">Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cc15-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
