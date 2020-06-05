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
# <a name="derived-math-functions-visual-basic"></a>Abgeleitete mathematische Funktionen (Visual Basic)
In der folgenden Tabelle werden nicht systeminterne mathematische Funktionen gezeigt, die von den intrinsischen mathematischen Funktionen des-Objekts abgeleitet werden können <xref:System.Math?displayProperty=nameWithType> . Sie können auf die intrinsischen mathematischen Funktionen zugreifen `Imports System.Math` , indem Sie Ihrer Datei oder Ihrem Projekt hinzufügen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Mathematische Funktionen](../functions/math-functions.md)
