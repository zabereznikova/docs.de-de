---
title: <proceduresignature1> überlädt '<proceduresignature2>', unterscheidet sich jedoch nur durch Array-von-Array-Parametertypen oder durch den Rang der Arrayparametertypen davon und ist daher nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 9006e12838581a98c7e7945278c7d767a3074259
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661777"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>\<proceduresignature1 > ist nicht CLS-kompatibel, da sie überlädt \<proceduresignature2 >, unterscheidet sich jedoch nur durch Array-von-Array-Parametertypen oder durch den Rang der Arrayparametertypen davon
Eine Prozedur oder Eigenschaft wird als markiert `<CLSCompliant(True)>` wenn er überschreibt, eine andere Prozedur bzw. Eigenschaft und der einzige Unterschied zwischen zugehörigen Parameterlisten der Schachtelungsebene eines verzweigten Arrays oder den Rang eines Arrays.  
  
 In den folgenden Deklarationen generieren die zweiten und dritten Deklarationen für diesen Fehler.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 Die zweite Deklaration ändert den ursprünglichen eindimensionalen Parameter `arrayParam` in ein Array von Arrays. Die dritte Deklaration ändert `arrayParam` in ein zweidimensionales Array (Rang 2). Während Visual Basic Überladungen, um nur eine dieser Änderungen unterscheiden können, diese Überladung ist nicht kompatibel mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40035  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie CLS-Kompatibilität benötigen, definieren Sie Ihre Überladungen, um auf vielfältigere Weise als nur die Änderungen, die auf dieser Hilfeseite genannten voneinander abweichen.  
  
- Wenn Sie festlegen, dass die Überladungen unterscheiden sich nur durch die Änderungen, die auf diese Hilfe erwähnten Seite, entfernen Sie die <xref:System.CLSCompliantAttribute> von den Definitionen, oder markieren Sie sie als `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Siehe auch

- [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
