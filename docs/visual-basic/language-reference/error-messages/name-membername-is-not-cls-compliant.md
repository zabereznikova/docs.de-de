---
title: Name "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 43fff3f12295f3837148b0a349887e8405126819
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160235"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a>BC40031: der Name \<membername> ist nicht CLS-kompatibel.

Eine Assembly ist als gekennzeichnet `<CLSCompliant(True)>` , macht jedoch einen Member mit einem Namen verfügbar, der mit einem Unterstrich beginnt ( `_` ).

 Ein Programmier Element kann einen oder mehrere Unterstriche enthalten, muss jedoch nicht mit einem Unterstrich beginnen, um mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel zu sein. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.

 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.

 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC40031

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Elementnamen so, dass er nicht mit einem Unterstrich beginnt.

- Wenn der Elementname unverändert bleiben muss, entfernen Sie den <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie ihn als `<CLSCompliant(False)>` . Sie können die Assembly weiterhin als markieren `<CLSCompliant(True)>` .

## <a name="see-also"></a>Siehe auch

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Benennungskonventionen in Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
