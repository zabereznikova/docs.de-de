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
# <a name="derived-math-functions-visual-basic"></a>Abgeleitete mathematische Funktionen (Visual Basic)
In der folgenden Tabelle werden nicht systeminterne mathematische Funktionen gezeigt, die von den intrinsischen mathematischen Funktionen des <xref:System.Math?displayProperty=nameWithType> Objekts abgeleitet werden können. Sie können auf die intrinsischen mathematischen Funktionen zugreifen, indem Sie Ihrer Datei oder Ihrem Projekt `Imports System.Math` hinzufügen.  
  
|Funktion|Abgeleitete Entsprechungen|  
|--------------|-------------------------|  
|Secant (Sek. (x))|1/cos (x)|  
|Cosecant (CSC (x))|1/sin (x)|  
|Kotangens (CTAN (x))|1/tan (x)|  
|Umgekehrter Sinus (Asin (x))|Atan (x/sqrt (-x * x + 1))|  
|Umgekehrter Kosinus (acos (x))|Atan (-x/sqrt (-x * x + 1)) + 2 \* Atan (1)|  
|Inverse Sekans (ASEC (x))|2 * Atan (1) – Atan (Vorzeichen (x)/sqrt (x \* x – 1))|  
|Umgekehrter kosecant (Acsc (x))|Atan (Vorzeichen (x)/sqrt (x * x – 1))|  
|Umgekehrter Kotangens (Acot (x))|2 * Atan (1)-Atan (x)|  
|Hyperbolischer Sinus (sinh (x))|(Exp (x) – Exp (-x))/2|  
|Hyperbolischer Kosinus (cosh (x))|(Exp (x) + Exp (-x))/2|  
|Hyperbolischer Tangens (tanh (x))|(Exp (x) – Exp (-x))/(Exp (x) + Exp (-x))|  
|Hyperbolischer Sekans (Sech (x))|2/(Exp (x) + Exp (-x))|  
|Hyperbolischer kosecant (csch (x))|2/(Exp (x) – Exp (-x))|  
|Hyperbolischer Kotangens (Koth (x))|(Exp (x) + Exp (-x))/(Exp (x) – Exp (-x))|  
|Umgekehrter hyperbolischer Sinus (asinh (x))|Log (x + sqrt (x * x + 1))|  
|Umgekehrter hyperbolischer Kosinus (acosh (x))|Log (x + sqrt (x * x – 1))|  
|Umgekehrter hyperbolischer Tangens (atanh (x))|Log ((1 + x)/(1 – x))/2|  
|Umgekehrter hyperbolischer Sekans (AsecH (x))|Log ((sqrt (-x * x + 1) + 1)/x)|  
|Umgekehrter hyperbolischer kosecant (acsch (x))|Log ((Vorzeichen (x) * sqrt (x \* x + 1) + 1)/x)|  
|Umgekehrter hyperbolischer Kotangens (acoth (x))|Log ((x + 1)/(x – 1))/2|  
  
## <a name="see-also"></a>Siehe auch

- [Mathematische Funktionen](../../../visual-basic/language-reference/functions/math-functions.md)
