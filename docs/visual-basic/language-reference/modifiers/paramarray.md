---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Gibt an, dass ein Prozedurparameter, ein optionales Array von Elementen des angegebenen Typs akzeptiert. `ParamArray`kann nur für den letzten Parameter einer Parameterliste verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 `ParamArray`können Sie eine beliebige Anzahl von Argumenten an die Prozedur übergeben. Ein `ParamArray` Parameter ist immer mit deklarierten [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
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
