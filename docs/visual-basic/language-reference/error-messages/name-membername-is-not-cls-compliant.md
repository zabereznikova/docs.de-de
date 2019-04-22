---
title: Name "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 06b20b4f61741f2174654d749df55c3c4348c547
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824623"
---
# <a name="name-membername-is-not-cls-compliant"></a>Namen \<Membername > ist nicht CLS-kompatibel.
Eine Assembly ist als markiert `<CLSCompliant(True)>` aber zur Verfügung stellt ein Element mit einem Namen, die mit einem Unterstrich beginnt (`_`).  
  
 Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, jedoch werden zur Einhaltung der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), es muss nicht mit einem Unterstrich beginnen. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40031  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Namen des Members, damit er nicht mit einem Unterstrich beginnt.  
  
-   Wenn Sie der Namen des Members unveränderte verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`. Sie können weiterhin markieren Sie die Assembly als `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>Siehe auch

- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
