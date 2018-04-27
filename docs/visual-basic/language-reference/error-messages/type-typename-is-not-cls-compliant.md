---
title: Typ &lt;Typename&gt; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73abc8b055e7eb9d1a4f6917d816cab5b4509f86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a>Typ &lt;Typename&gt; ist nicht CLS-kompatibel.
Eine Variable, Eigenschaft oder Funktionsrückgabe ist mit einem Datentyp deklariert, der nicht CLS-kompatibel ist.  
  
 Für eine Anwendung einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), müssen sie nur CLS-kompatible Typen verwenden.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Fehler-ID:** BC40041  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Ihre Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp dieses Elements in den ähnlichsten CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Wenn Ihre Anwendung nicht CLS-kompatibel sein muss, müssen Sie nicht ändert nichts. Sie sollten jedoch seine Nichtkompatibilität bewusst sein.