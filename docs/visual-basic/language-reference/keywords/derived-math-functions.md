---
title: Abgeleitete mathematische Funktionen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836583"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="8ffac-102">Abgeleitete mathematische Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ffac-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="8ffac-103">Die folgende Tabelle zeigt den nicht systeminternen mathematische Funktionen, die von systeminternen mathematischen Funktionen abgeleitet werden, können die <xref:System.Math?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="8ffac-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="8ffac-104">Sie können die systeminternen mathematischen Funktionen zugreifen, indem hinzufügen `Imports System.Math` Ihrer Datei oder das Projekt.</span><span class="sxs-lookup"><span data-stu-id="8ffac-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="8ffac-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="8ffac-105">Function</span></span>|<span data-ttu-id="8ffac-106">Abgeleitete Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="8ffac-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="8ffac-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-107">Secant (Sec(x))</span></span>|<span data-ttu-id="8ffac-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="8ffac-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="8ffac-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="8ffac-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="8ffac-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="8ffac-111">Kotangens (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="8ffac-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="8ffac-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="8ffac-113">Arkussinus (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="8ffac-114">Atan (X / Sqrt (-X \* X + 1))</span><span class="sxs-lookup"><span data-stu-id="8ffac-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="8ffac-115">Arkuskosinus (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="8ffac-116">Atan (-X / Sqrt (-X \* X + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="8ffac-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="8ffac-117">Inverse sekans (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="8ffac-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (X \* x-1))</span><span class="sxs-lookup"><span data-stu-id="8ffac-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="8ffac-119">Inverse kosekans (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="8ffac-120">Atan(Sign(x) / Sqrt (X \* x-1))</span><span class="sxs-lookup"><span data-stu-id="8ffac-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="8ffac-121">Umgekehrten Kotangens (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="8ffac-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="8ffac-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="8ffac-123">Der Hyperbelsinus (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="8ffac-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ffac-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="8ffac-125">Hyperbolischer Kosinus (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="8ffac-126">(Exp(x) + eingesetzte / 2</span><span class="sxs-lookup"><span data-stu-id="8ffac-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="8ffac-127">Hyperbolischer Tangens (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="8ffac-128">(Exp(x) – eingesetzte / (Exp(x) + eingesetzte</span><span class="sxs-lookup"><span data-stu-id="8ffac-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="8ffac-129">Hyperbolischen sekans (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="8ffac-130">2 / (Exp(x) + eingesetzte</span><span class="sxs-lookup"><span data-stu-id="8ffac-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="8ffac-131">Hypberbolischen kosekans (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="8ffac-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="8ffac-133">Hyperbolischen Kotangens (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="8ffac-134">(Exp(x) + eingesetzte / (Exp(x) – eingesetzte</span><span class="sxs-lookup"><span data-stu-id="8ffac-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="8ffac-135">Umgekehrter hyperbolischer Sinus (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="8ffac-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="8ffac-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="8ffac-137">Umgekehrter hyperbolischer Kosinus (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="8ffac-138">Protokoll (X + "SQRT" (X \* x-1))</span><span class="sxs-lookup"><span data-stu-id="8ffac-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="8ffac-139">Umgekehrte hyperbolische Tangens (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="8ffac-140">Log ((1 + x) / (1: X)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ffac-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="8ffac-141">Umgekehrten hyperbolischen sekans (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="8ffac-142">Log (("SQRT" (-X \* X + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="8ffac-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="8ffac-143">Umgekehrten hyperbolischen kosekans (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="8ffac-144">Log((Sign(x) \* Sqrt (X \* X + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="8ffac-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="8ffac-145">Umgekehrten hyperbolischen Kotangens (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="8ffac-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="8ffac-146">Log ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ffac-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ffac-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ffac-147">See also</span></span>

- [<span data-ttu-id="8ffac-148">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8ffac-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
