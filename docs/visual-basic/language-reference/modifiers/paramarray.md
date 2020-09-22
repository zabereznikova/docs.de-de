---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: baf9303101eea9eed27e8a4eee9e04d255c798e9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867828"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)

Gibt an, dass ein Prozedur Parameter ein optionales Array von Elementen vom angegebenen Typ annimmt. `ParamArray` kann nur für den letzten Parameter einer Parameterliste verwendet werden.  
  
## <a name="remarks"></a>Bemerkungen  

 `ParamArray` ermöglicht es Ihnen, eine beliebige Anzahl von Argumenten an die Prozedur zu übergeben. Ein `ParamArray` Parameter wird immer mit [ByVal](byval.md)deklariert.  
  
 Sie können ein oder mehrere Argumente für einen Parameter angeben, `ParamArray` indem Sie ein Array des entsprechenden Datentyps, eine durch Trennzeichen getrennte Liste von Werten oder überhaupt nichts übergeben. Weitere Informationen finden Sie unter "Aufrufen eines ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird. Wenn Sie ein Parameter Array aus dem aufrufenden Code akzeptieren, sollten Sie seine Länge testen und entsprechende Schritte ausführen, wenn es für Ihre Anwendung zu groß ist.  
  
 Der `ParamArray`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Function-Anweisung](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Sub-Anweisung](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselwörter](../keywords/index.md)
- [Parameterarrays](../../programming-guide/language-features/procedures/parameter-arrays.md)
