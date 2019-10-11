---
title: <proceduresignature1> überlädt '<proceduresignature2>', unterscheidet sich jedoch nur durch Array-von-Array-Parametertypen oder durch den Rang der Arrayparametertypen davon und ist daher nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250179"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>\<proceduresignature1 > ist nicht CLS-kompatibel, da die \<proceduresignature2-> überlastet ist, die sich nur durch Array von Array Parametertypen oder durch den Rang der Array Parametertypen unterscheidet.

Eine Prozedur oder Eigenschaft wird als `<CLSCompliant(True)>` gekennzeichnet, wenn Sie eine andere Prozedur oder Eigenschaft überschreibt und der einzige Unterschied zwischen den Parameterlisten die Schachtelungs Ebene einer Jagged Array oder der Rangfolge eines Arrays ist.
  
 In den folgenden Deklarationen wird dieser Fehler durch die zweite und dritte Deklaration generiert:
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 Die zweite Deklaration ändert den ursprünglichen eindimensionalen Parameter `arrayParam` in ein Array von Arrays. Die dritte Deklaration ändert `arrayParam` in ein zweidimensionales Array (Rang 2). Obwohl Visual Basic die über Ladungen nur durch eine dieser Änderungen unterscheiden kann, ist das überladen mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) nicht kompatibel.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40035  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie CLS-Kompatibilität benötigen, definieren Sie die über Ladungen so, dass Sie sich auf mehr Weise voneinander unterscheiden als nur die Änderungen, die auf dieser Hilfeseite aufgeführt sind.
- Wenn Sie festlegen möchten, dass die über Ladungen nur durch die auf dieser Hilfeseite genannten Änderungen voneinander abweichen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus ihren Definitionen, oder markieren Sie Sie als `<CLSCompliant(False)>`.
  
## <a name="see-also"></a>Siehe auch

- [Prozedurüberladung](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Overloads](../modifiers/overloads.md)
