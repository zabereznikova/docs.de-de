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
ms.openlocfilehash: f84b1ef18ef2a924bb2e47da85ecbb51f982873a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869019"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="e33e9-102">Abgeleitete mathematische Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e33e9-102">Derived Math Functions (Visual Basic)</span></span>

<span data-ttu-id="e33e9-103">In der folgenden Tabelle werden nicht systeminterne mathematische Funktionen gezeigt, die von den intrinsischen mathematischen Funktionen des-Objekts abgeleitet werden können <xref:System.Math?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e33e9-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="e33e9-104">Sie können auf die intrinsischen mathematischen Funktionen zugreifen `Imports System.Math` , indem Sie Ihrer Datei oder Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e33e9-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="e33e9-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="e33e9-105">Function</span></span>|<span data-ttu-id="e33e9-106">Abgeleitete Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="e33e9-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="e33e9-107">Secant (Sek. (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-107">Secant (Sec(x))</span></span>|<span data-ttu-id="e33e9-108">1/cos (x)</span><span class="sxs-lookup"><span data-stu-id="e33e9-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="e33e9-109">Cosecant (CSC (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="e33e9-110">1/sin (x)</span><span class="sxs-lookup"><span data-stu-id="e33e9-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="e33e9-111">Kotangens (CTAN (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="e33e9-112">1/tan (x)</span><span class="sxs-lookup"><span data-stu-id="e33e9-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="e33e9-113">Umgekehrter Sinus (Asin (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="e33e9-114">Atan (x/sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="e33e9-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="e33e9-115">Umgekehrter Kosinus (acos (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="e33e9-116">Atan (-x/sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="e33e9-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="e33e9-117">Inverse Sekans (ASEC (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="e33e9-118">2 \* Atan (1) – Atan (Vorzeichen (x)/sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="e33e9-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="e33e9-119">Umgekehrter kosecant (Acsc (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="e33e9-120">Atan (Vorzeichen (x)/sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="e33e9-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="e33e9-121">Umgekehrter Kotangens (Acot (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="e33e9-122">2 \* Atan (1)-Atan (x)</span><span class="sxs-lookup"><span data-stu-id="e33e9-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="e33e9-123">Hyperbolischer Sinus (sinh (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="e33e9-124">(Exp (x) – Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="e33e9-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="e33e9-125">Hyperbolischer Kosinus (cosh (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="e33e9-126">(Exp (x) + Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="e33e9-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="e33e9-127">Hyperbolischer Tangens (tanh (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="e33e9-128">(Exp (x) – Exp (-x))/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="e33e9-129">Hyperbolischer Sekans (Sech (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="e33e9-130">2/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="e33e9-131">Hyperbolischer kosecant (csch (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="e33e9-132">2/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="e33e9-133">Hyperbolischer Kotangens (Koth (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="e33e9-134">(Exp (x) + Exp (-x))/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="e33e9-135">Umgekehrter hyperbolischer Sinus (asinh (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="e33e9-136">Log (x + sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="e33e9-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="e33e9-137">Umgekehrter hyperbolischer Kosinus (acosh (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="e33e9-138">Log (x + sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="e33e9-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="e33e9-139">Umgekehrter hyperbolischer Tangens (atanh (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="e33e9-140">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="e33e9-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="e33e9-141">Umgekehrter hyperbolischer Sekans (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="e33e9-142">Log ((sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="e33e9-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="e33e9-143">Umgekehrter hyperbolischer kosecant (acsch (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="e33e9-144">Log ((Vorzeichen (x) \* sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="e33e9-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="e33e9-145">Umgekehrter hyperbolischer Kotangens (acoth (x))</span><span class="sxs-lookup"><span data-stu-id="e33e9-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="e33e9-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="e33e9-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e33e9-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e33e9-147">See also</span></span>

- [<span data-ttu-id="e33e9-148">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="e33e9-148">Math Functions</span></span>](../functions/math-functions.md)
