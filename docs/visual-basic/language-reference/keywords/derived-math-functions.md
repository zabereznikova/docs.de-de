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
# <a name="derived-math-functions-visual-basic"></a>Abgeleitete mathematische Funktionen (Visual Basic)
Die folgende Tabelle zeigt den nicht systeminternen mathematische Funktionen, die von systeminternen mathematischen Funktionen abgeleitet werden, können die <xref:System.Math?displayProperty=nameWithType> Objekt. Sie können die systeminternen mathematischen Funktionen zugreifen, indem hinzufügen `Imports System.Math` Ihrer Datei oder das Projekt.  
  
|Funktion|Abgeleitete Entsprechungen|  
|--------------|-------------------------|  
|Secant (Sec(x))|1 / Cos(x)|  
|Cosecant (Csc(x))|1 / Sin(x)|  
|Kotangens (Ctan(x))|1 / Tan(x)|  
|Arkussinus (Asin(x))|Atan (X / Sqrt (-X * X + 1))|  
|Arkuskosinus (Acos(x))|Atan (-X / Sqrt (-X * X + 1)) + 2 \* Atan(1)|  
|Inverse sekans (Asec(x))|2 * Atan(1) – Atan(Sign(x) / Sqrt (X \* x-1))|  
|Inverse kosekans (Acsc(x))|Atan(Sign(x) / Sqrt (X * x-1))|  
|Umgekehrten Kotangens (Acot(x))|2 * Atan(1) - Atan(x)|  
|Der Hyperbelsinus (Sinh(x))|(Exp(x) – Exp(-x)) / 2|  
|Hyperbolischer Kosinus (Cosh(x))|(Exp(x) + eingesetzte / 2|  
|Hyperbolischer Tangens (Tanh(x))|(Exp(x) – eingesetzte / (Exp(x) + eingesetzte|  
|Hyperbolischen sekans (Sech(x))|2 / (Exp(x) + eingesetzte|  
|Hypberbolischen kosekans (Csch(x))|2 / (Exp(x) – Exp(-x))|  
|Hyperbolischen Kotangens (Coth(x))|(Exp(x) + eingesetzte / (Exp(x) – eingesetzte|  
|Umgekehrter hyperbolischer Sinus (Asinh(x))|Log(x + Sqrt(x * x + 1))|  
|Umgekehrter hyperbolischer Kosinus (Acosh(x))|Protokoll (X + "SQRT" (X * x-1))|  
|Umgekehrte hyperbolische Tangens (Atanh(x))|Log ((1 + x) / (1: X)) / 2|  
|Umgekehrten hyperbolischen sekans (AsecH(x))|Log (("SQRT" (-X * X + 1) + 1) / x)|  
|Umgekehrten hyperbolischen kosekans (Acsch(x))|Log((Sign(x) * Sqrt (X \* X + 1) + 1) / x)|  
|Umgekehrten hyperbolischen Kotangens (Acoth(x))|Log ((x + 1) / (x-1)) / 2|  
  
## <a name="see-also"></a>Siehe auch

- [Mathematische Funktionen](../../../visual-basic/language-reference/functions/math-functions.md)
