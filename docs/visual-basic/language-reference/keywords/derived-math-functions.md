---
title: Abgeleitete mathematische Funktionen
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
ms.openlocfilehash: 73cf56dd72f2baac0474d6f5c4e88228a1fe38cf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349855"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="766a7-102">Abgeleitete mathematische Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="766a7-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="766a7-103">In der folgenden Tabelle werden nicht systeminterne mathematische Funktionen gezeigt, die von den intrinsischen mathematischen Funktionen des <xref:System.Math?displayProperty=nameWithType> Objekts abgeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="766a7-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="766a7-104">Sie können auf die intrinsischen mathematischen Funktionen zugreifen, indem Sie Ihrer Datei oder Ihrem Projekt `Imports System.Math` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="766a7-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="766a7-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="766a7-105">Function</span></span>|<span data-ttu-id="766a7-106">Abgeleitete Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="766a7-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="766a7-107">Secant (Sek. (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-107">Secant (Sec(x))</span></span>|<span data-ttu-id="766a7-108">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="766a7-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="766a7-109">Cosecant (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="766a7-110">1/sin (x)</span><span class="sxs-lookup"><span data-stu-id="766a7-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="766a7-111">Kotangens (CTAN (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="766a7-112">1/tan (x)</span><span class="sxs-lookup"><span data-stu-id="766a7-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="766a7-113">Umgekehrter Sinus (Asin (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="766a7-114">Atan (x/sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="766a7-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="766a7-115">Umgekehrter Kosinus (acos (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="766a7-116">Atan (-x/sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="766a7-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="766a7-117">Inverse Sekans (ASEC (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="766a7-118">2 \* Atan (1) – Atan (Vorzeichen (x)/sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="766a7-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="766a7-119">Umgekehrter kosecant (Acsc (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="766a7-120">Atan (Vorzeichen (x)/sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="766a7-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="766a7-121">Umgekehrter Kotangens (Acot (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="766a7-122">2 \* Atan (1)-Atan (x)</span><span class="sxs-lookup"><span data-stu-id="766a7-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="766a7-123">Hyperbolischer Sinus (sinh (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="766a7-124">(Exp (x) – Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="766a7-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="766a7-125">Hyperbolischer Kosinus (cosh (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="766a7-126">(Exp (x) + Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="766a7-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="766a7-127">Hyperbolischer Tangens (tanh (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="766a7-128">(Exp (x) – Exp (-x))/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="766a7-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="766a7-129">Hyperbolischer Sekans (Sech (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="766a7-130">2/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="766a7-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="766a7-131">Hyperbolischer kosecant (csch (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="766a7-132">2/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="766a7-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="766a7-133">Hyperbolischer Kotangens (Koth (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="766a7-134">(Exp (x) + Exp (-x))/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="766a7-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="766a7-135">Umgekehrter hyperbolischer Sinus (asinh (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="766a7-136">Log (x + sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="766a7-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="766a7-137">Umgekehrter hyperbolischer Kosinus (acosh (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="766a7-138">Log (x + sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="766a7-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="766a7-139">Umgekehrter hyperbolischer Tangens (atanh (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="766a7-140">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="766a7-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="766a7-141">Umgekehrter hyperbolischer Sekans (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="766a7-142">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="766a7-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="766a7-143">Umgekehrter hyperbolischer kosecant (acsch (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="766a7-144">Log ((Vorzeichen (x) \* sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="766a7-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="766a7-145">Umgekehrter hyperbolischer Kotangens (acoth (x))</span><span class="sxs-lookup"><span data-stu-id="766a7-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="766a7-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="766a7-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="766a7-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="766a7-147">See also</span></span>

- [<span data-ttu-id="766a7-148">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="766a7-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
