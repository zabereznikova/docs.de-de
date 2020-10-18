---
title: <membername> ist nicht CLS-kompatibel und darf in einer CLS-kompatiblen Schnittstelle nicht verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: aa7944e90857436553435ce783c0820770496a49
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159988"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>BC40033: nicht CLS-kompatibel \<membername> ist in einer CLS-kompatiblen Schnittstelle nicht zulässig.

Eine Eigenschaft, Prozedur oder ein Ereignis in einer Schnittstelle wird als gekennzeichnet, `<CLSCompliant(True)>` Wenn die Schnittstelle selbst als gekennzeichnet ist `<CLSCompliant(False)>` oder nicht markiert ist.

 Damit eine Schnittstelle mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, müssen alle Mitglieder kompatibel sein.

 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.

 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.

 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC40033

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn Sie CLS-Kompatibilität benötigen und die Kontrolle über den Quellcode der Schnittstelle haben, markieren Sie die Schnittstelle so, als `<CLSCompliant(True)>` ob alle zugehörigen Member kompatibel sind.

- Wenn Sie CLS-Kompatibilität benötigen und keine Kontrolle über den Quellcode der Schnittstelle haben, oder wenn er nicht als kompatibel eingestuft wird, definieren Sie diesen Member in einer anderen Schnittstelle.

- Wenn Sie möchten, dass dieser Member in der aktuellen Schnittstelle verbleibt, entfernen Sie <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie Sie als `<CLSCompliant(False)>` .

## <a name="see-also"></a>Siehe auch

- [Interface-Anweisung](../statements/interface-statement.md)
