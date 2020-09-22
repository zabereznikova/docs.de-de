---
title: Name "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 33b60b2212d25737330dc93d7ba2715e4d5865b7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873707"
---
# <a name="name-membername-is-not-cls-compliant"></a>Name "\<membername>" ist nicht CLS-kompatibel.

Eine Assembly ist als gekennzeichnet `<CLSCompliant(True)>` , macht jedoch einen Member mit einem Namen verfügbar, der mit einem Unterstrich beginnt ( `_` ).  
  
 Ein Programmier Element kann ein oder mehrere Unterstriche enthalten, aber damit es mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf es nicht mit einem Unterstrich beginnen. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40031  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Elementnamen so, dass er nicht mit einem Unterstrich beginnt.  
  
- Wenn der Elementname unverändert bleiben muss, entfernen Sie den <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie ihn als `<CLSCompliant(False)>` . Sie können die Assembly weiterhin als markieren `<CLSCompliant(True)>` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Benennungskonventionen in Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
