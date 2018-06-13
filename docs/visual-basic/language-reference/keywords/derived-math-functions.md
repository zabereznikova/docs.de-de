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
ms.openlocfilehash: 87faa623f5b145eec8b88e350fce4171125324dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596807"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="af7e8-102">Abgeleitete mathematische Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af7e8-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="af7e8-103">Die folgende Tabelle zeigt den nicht systeminternen mathematische Funktionen, die von systeminternen mathematischen Funktionen abgeleitet werden, können die <xref:System.Math?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="af7e8-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="af7e8-104">Sie können die systeminternen mathematischen Funktionen zugreifen, indem hinzufügen `Imports System.Math` zur Datei oder zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="af7e8-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="af7e8-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="af7e8-105">Function</span></span>|<span data-ttu-id="af7e8-106">Abgeleitete äquivalente</span><span class="sxs-lookup"><span data-stu-id="af7e8-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="af7e8-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-107">Secant (Sec(x))</span></span>|<span data-ttu-id="af7e8-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="af7e8-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="af7e8-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="af7e8-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="af7e8-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="af7e8-111">Kotangens (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="af7e8-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="af7e8-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="af7e8-113">Arkussinus (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="af7e8-114">Atan (X / Sqrt (-X \* X + 1))</span><span class="sxs-lookup"><span data-stu-id="af7e8-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="af7e8-115">Umgekehrte Kosinus (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="af7e8-116">Atan (-X / Sqrt (-X * X + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="af7e8-116">Atan(-x / Sqrt(-x * x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="af7e8-117">Inverse sekans (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="af7e8-118">2 * Atan(1) – Atan(Sign(x) / Sqrt (X \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="af7e8-118">2 * Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="af7e8-119">Inverse kosekans (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="af7e8-120">Atan(Sign(x) / Sqrt (X \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="af7e8-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="af7e8-121">Umgekehrten Kotangens (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="af7e8-122">2 \* Atan(1) - ARCTAN(x)</span><span class="sxs-lookup"><span data-stu-id="af7e8-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="af7e8-123">Hyperbolischer Sinus (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="af7e8-124">(Exp(x) – eingesetzte / 2</span><span class="sxs-lookup"><span data-stu-id="af7e8-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="af7e8-125">Hyperbolischer Kosinus (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="af7e8-126">(Exp(x) + eingesetzte / 2</span><span class="sxs-lookup"><span data-stu-id="af7e8-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="af7e8-127">Hyperbolischer Tangens (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="af7e8-128">(Exp(x) – eingesetzte / (Exp(x) + eingesetzte</span><span class="sxs-lookup"><span data-stu-id="af7e8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="af7e8-129">Hyperbolischen sekans (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="af7e8-130">2 / (Exp(x) + eingesetzte</span><span class="sxs-lookup"><span data-stu-id="af7e8-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="af7e8-131">Hypberbolischen kosekans (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="af7e8-132">2 / (Exp(x) – eingesetzte</span><span class="sxs-lookup"><span data-stu-id="af7e8-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="af7e8-133">Hyperbolischen Kotangens (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="af7e8-134">(Exp(x) + eingesetzte / (Exp(x) – eingesetzte</span><span class="sxs-lookup"><span data-stu-id="af7e8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="af7e8-135">Umgekehrter hyperbolischer Sinus (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="af7e8-136">Protokoll (X + Sqrt (X \* X + 1))</span><span class="sxs-lookup"><span data-stu-id="af7e8-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="af7e8-137">Umgekehrter hyperbolischer Kosinus (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="af7e8-138">Protokoll (X + Sqrt (X \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="af7e8-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="af7e8-139">Umgekehrter hyperbolischer Tangens (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="af7e8-140">Protokoll ((1 + x) / (1 – X)) / 2</span><span class="sxs-lookup"><span data-stu-id="af7e8-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="af7e8-141">Umgekehrten hyperbolischen sekans (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="af7e8-142">Log ((Sqrt (-X \* X + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="af7e8-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="af7e8-143">Umgekehrten hyperbolischen kosekans (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="af7e8-144">Log((Sign(x) * Sqrt (X \* X + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="af7e8-144">Log((Sign(x) * Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="af7e8-145">Umgekehrten hyperbolischen Kotangens (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="af7e8-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="af7e8-146">Protokoll ((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="af7e8-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af7e8-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af7e8-147">See Also</span></span>  
 [<span data-ttu-id="af7e8-148">Mathematische Funktionen</span><span class="sxs-lookup"><span data-stu-id="af7e8-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
