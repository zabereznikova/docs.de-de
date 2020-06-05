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
ms.openlocfilehash: 611f3d8faf2148b8a983467d9ace4fd6c18b30e6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373884"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="f0e60-102">Abgeleitete mathematische Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0e60-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="f0e60-103">In der folgenden Tabelle werden nicht systeminterne mathematische Funktionen gezeigt, die von den intrinsischen mathematischen Funktionen des-Objekts abgeleitet werden können <xref:System.Math?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f0e60-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="f0e60-104">Sie können auf die intrinsischen mathematischen Funktionen zugreifen `Imports System.Math` , indem Sie Ihrer Datei oder Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0e60-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="f0e60-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="f0e60-105">Function</span></span>|<span data-ttu-id="f0e60-106">Abgeleitete Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="f0e60-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="f0e60-107">Secant (Sek. (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-107">Secant (Sec(x))</span></span>|<span data-ttu-id="f0e60-108">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="f0e60-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="f0e60-109">Cosecant (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="f0e60-110">1/sin (x)</span><span class="sxs-lookup"><span data-stu-id="f0e60-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="f0e60-111">Kotangens (CTAN (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="f0e60-112">1/tan (x)</span><span class="sxs-lookup"><span data-stu-id="f0e60-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="f0e60-113">Umgekehrter Sinus (Asin (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="f0e60-114">Atan (x/sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="f0e60-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="f0e60-115">Umgekehrter Kosinus (acos (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="f0e60-116">Atan (-x/sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="f0e60-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="f0e60-117">Inverse Sekans (ASEC (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="f0e60-118">2 \* Atan (1) – Atan (Vorzeichen (x)/sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="f0e60-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="f0e60-119">Umgekehrter kosecant (Acsc (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="f0e60-120">Atan (Vorzeichen (x)/sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="f0e60-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="f0e60-121">Umgekehrter Kotangens (Acot (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="f0e60-122">2 \* Atan (1)-Atan (x)</span><span class="sxs-lookup"><span data-stu-id="f0e60-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="f0e60-123">Hyperbolischer Sinus (sinh (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="f0e60-124">(Exp (x) – Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="f0e60-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="f0e60-125">Hyperbolischer Kosinus (cosh (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="f0e60-126">(Exp (x) + Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="f0e60-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="f0e60-127">Hyperbolischer Tangens (tanh (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="f0e60-128">(Exp (x) – Exp (-x))/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="f0e60-129">Hyperbolischer Sekans (Sech (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="f0e60-130">2/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="f0e60-131">Hyperbolischer kosecant (csch (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="f0e60-132">2/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="f0e60-133">Hyperbolischer Kotangens (Koth (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="f0e60-134">(Exp (x) + Exp (-x))/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="f0e60-135">Umgekehrter hyperbolischer Sinus (asinh (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="f0e60-136">Log (x + sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="f0e60-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="f0e60-137">Umgekehrter hyperbolischer Kosinus (acosh (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="f0e60-138">Log (x + sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="f0e60-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="f0e60-139">Umgekehrter hyperbolischer Tangens (atanh (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="f0e60-140">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="f0e60-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="f0e60-141">Umgekehrter hyperbolischer Sekans (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="f0e60-142">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="f0e60-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="f0e60-143">Umgekehrter hyperbolischer kosecant (acsch (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="f0e60-144">Log ((Vorzeichen (x) \* sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="f0e60-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="f0e60-145">Umgekehrter hyperbolischer Kotangens (acoth (x))</span><span class="sxs-lookup"><span data-stu-id="f0e60-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="f0e60-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="f0e60-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0e60-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0e60-147">See also</span></span>

- [<span data-ttu-id="f0e60-148">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="f0e60-148">Math Functions</span></span>](../functions/math-functions.md)
