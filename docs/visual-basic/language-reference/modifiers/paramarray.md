---
title: ByRef
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: fbc87bffebc265e6062512e96fc29a64334b3c65
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351370"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Gibt an, dass ein Prozedur Parameter ein optionales Array von Elementen vom angegebenen Typ annimmt. `ParamArray` können nur für den letzten Parameter einer Parameterliste verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 `ParamArray` ermöglicht es Ihnen, eine beliebige Anzahl von Argumenten an die Prozedur zu übergeben. Ein `ParamArray` Parameter wird immer mit [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)deklariert.  
  
 Sie können einem `ParamArray` Parameter ein oder mehrere Argumente bereitstellen, indem Sie ein Array des entsprechenden Datentyps, eine durch Trennzeichen getrennte Liste von Werten oder überhaupt nichts übergeben. Weitere Informationen finden Sie unter "Aufrufen eines ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird. Wenn Sie ein Parameter Array aus dem aufrufenden Code akzeptieren, sollten Sie seine Länge testen und entsprechende Schritte ausführen, wenn es für Ihre Anwendung zu groß ist.  
  
 Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Parameterarrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
