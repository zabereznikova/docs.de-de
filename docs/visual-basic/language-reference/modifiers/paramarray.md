---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: be8ddb7f9ba08535d12890d1c5c82a9b7b485f3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597359"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Gibt an, dass ein Prozedurparameter, ein optionales Array von Elementen des angegebenen Typs akzeptiert. `ParamArray` kann nur für den letzten Parameter einer Parameterliste verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 `ParamArray` können Sie eine beliebige Anzahl von Argumenten an die Prozedur übergeben. Ein `ParamArray` Parameter ist immer mit deklarierten [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Sie können angeben, dass ein oder mehrere Argumente an eine `ParamArray` Parameter durch Übergeben eines Arrays der entsprechenden Daten eingeben, eine durch Trennzeichen getrennte Liste von Werten oder nichts an. Weitere Informationen finden Sie unter "ParamArray aufrufen" in [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass einige interne Kapazität der Anwendung überschritten. Wenn Sie ein Parameterarray des aufrufenden Codes akzeptieren, sollten Sie seine Länge testen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.  
  
 Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)  
 [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
