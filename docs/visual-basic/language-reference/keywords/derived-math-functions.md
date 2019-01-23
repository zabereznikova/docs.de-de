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
ms.openlocfilehash: 1273871faf65afdd1a894c03f13a2c93507c1b13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505860"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="38d42-102">Abgeleitete mathematische Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38d42-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="38d42-103">Die folgende Tabelle zeigt den nicht systeminternen mathematische Funktionen, die von systeminternen mathematischen Funktionen abgeleitet werden, können die <xref:System.Math?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="38d42-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="38d42-104">Sie können die systeminternen mathematischen Funktionen zugreifen, indem hinzufügen `Imports System.Math` Ihrer Datei oder das Projekt.</span><span class="sxs-lookup"><span data-stu-id="38d42-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="38d42-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="38d42-105">Function</span></span>|<span data-ttu-id="38d42-106">Abgeleitete Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="38d42-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="38d42-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-107">Secant (Sec(x))</span></span>|<span data-ttu-id="38d42-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="38d42-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="38d42-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="38d42-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="38d42-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="38d42-111">Kotangens (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="38d42-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="38d42-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="38d42-113">Arkussinus (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="38d42-114">Atan (X / Sqrt (-X \* X + 1))</span><span class="sxs-lookup"><span data-stu-id="38d42-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="38d42-115">Arkuskosinus (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="38d42-116">Atan (-X / Sqrt (-X \* X + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="38d42-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="38d42-117">Inverse sekans (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="38d42-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (X \* x-1))</span><span class="sxs-lookup"><span data-stu-id="38d42-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="38d42-119">Inverse kosekans (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="38d42-120">Atan(Sign(x) / Sqrt (X \* x-1))</span><span class="sxs-lookup"><span data-stu-id="38d42-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="38d42-121">Umgekehrten Kotangens (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="38d42-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="38d42-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="38d42-123">Der Hyperbelsinus (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="38d42-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="38d42-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="38d42-125">Hyperbolischer Kosinus (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="38d42-126">(Exp(x) + eingesetzte / 2</span><span class="sxs-lookup"><span data-stu-id="38d42-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="38d42-127">Hyperbolischer Tangens (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="38d42-128">(Exp(x) – eingesetzte / (Exp(x) + eingesetzte</span><span class="sxs-lookup"><span data-stu-id="38d42-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="38d42-129">Hyperbolischen sekans (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="38d42-130">2 / (Exp(x) + eingesetzte</span><span class="sxs-lookup"><span data-stu-id="38d42-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="38d42-131">Hypberbolischen kosekans (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="38d42-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="38d42-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="38d42-133">Hyperbolischen Kotangens (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="38d42-134">(Exp(x) + eingesetzte / (Exp(x) – eingesetzte</span><span class="sxs-lookup"><span data-stu-id="38d42-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="38d42-135">Umgekehrter hyperbolischer Sinus (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="38d42-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="38d42-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="38d42-137">Umgekehrter hyperbolischer Kosinus (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="38d42-138">Protokoll (X + "SQRT" (X \* x-1))</span><span class="sxs-lookup"><span data-stu-id="38d42-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="38d42-139">Umgekehrte hyperbolische Tangens (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="38d42-140">Log ((1 + x) / (1: X)) / 2</span><span class="sxs-lookup"><span data-stu-id="38d42-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="38d42-141">Umgekehrten hyperbolischen sekans (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="38d42-142">Log (("SQRT" (-X \* X + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="38d42-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="38d42-143">Umgekehrten hyperbolischen kosekans (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="38d42-144">Log((Sign(x) \* Sqrt (X \* X + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="38d42-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="38d42-145">Umgekehrten hyperbolischen Kotangens (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="38d42-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="38d42-146">Log ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="38d42-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38d42-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38d42-147">See also</span></span>
- [<span data-ttu-id="38d42-148">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="38d42-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
