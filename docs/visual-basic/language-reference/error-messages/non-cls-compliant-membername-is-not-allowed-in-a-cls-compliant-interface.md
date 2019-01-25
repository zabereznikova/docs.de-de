---
title: Nicht-CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle nicht zulässig
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: c837065d2d448fc2523cfbd18efac962445f8bf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627694"
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Nicht-CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle nicht zulässig
Eine Eigenschaft, Prozedur oder das Ereignis in einer Schnittstelle als RuntimeCompatibility `<CLSCompliant(True)>` bei die Schnittstelle selbst als RuntimeCompatibility `<CLSCompliant(False)>` oder überhaupt nicht gekennzeichnet.  
  
 Für eine Schnittstelle zum Einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), alle seine Member müssen kompatibel sein.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40033  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie CLS-Kompatibilität benötigen und Kontrolle über den Quellcode für die Schnittstelle, markieren Sie die Schnittstelle als `<CLSCompliant(True)>` Wenn allen zugehörigen Membern kompatibel sind.  
  
-   Definieren Sie Wenn Sie CLS-Kompatibilität benötigen und haben keine Kontrolle über den Quellcode für die Schnittstelle, oder wenn dies nicht zutrifft, kompatibel sein müssen, dieses Elements in eine andere Schnittstelle aus.  
  
-   Wenn Sie dieses Element in der aktuellen Schnittstelle verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Siehe auch
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)

