---
title: "&lt;proceduresignature1&gt; ist nicht CLS-kompatibel, da sie überlädt &lt;proceduresignature2&gt; die unterscheidet sich jedoch nur durch Array von Arrayparametertypen oder durch den Rang der Array-Parametertypen"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords: BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d361759471a8edfa97437bd2503cfaa661fb9678
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; ist nicht CLS-kompatibel, da sie überlädt &lt;proceduresignature2&gt; die unterscheidet sich jedoch nur durch Array von Arrayparametertypen oder durch den Rang der Array-Parametertypen
Eine Prozedur oder Eigenschaft wird als gekennzeichnet `<CLSCompliant(True)>` Wenn sie eine andere Prozedur oder Eigenschaft überschreibt und des einzigen Unterschied zwischen ihren Parameterlisten der Schachtelungsebene eines verzweigten Arrays oder den Rang eines Arrays.  
  
 In den folgenden Deklarationen generieren die zweiten und dritten Deklarationen für diesen Fehler.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 Die zweite Deklaration ändert der ursprünglichen eindimensionalen Parameter `arrayParam` auf ein Array von Arrays. Die dritte Deklaration ändert `arrayParam` in ein zweidimensionales Array (Rang 2). Wenn Sie Visual Basic Überladungen auf, um nur eine dieser Änderungen unterscheiden können, solche überladen ist nicht kompatibel mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40035  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie CLS-Kompatibilität benötigen, definieren Sie die Überladungen, um auf vielfältigere Weise als nur die Änderungen, die auf dieser Hilfeseite sorgen voneinander abweichen.  
  
-   Wenn Sie verlangen, dass die Überladungen unterscheiden sich nur durch die Änderungen, die auf diese Hilfe erwähnten Seite, entfernen Sie die <xref:System.CLSCompliantAttribute> von ihren Definitionen, oder markieren Sie sie als `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Siehe auch  
   
 [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
