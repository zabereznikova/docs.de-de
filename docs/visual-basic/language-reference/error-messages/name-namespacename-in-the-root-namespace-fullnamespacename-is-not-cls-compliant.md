---
title: Der Name "<namespacename>" im Stammnamespace "<fullnamespacename>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 4e29a27841021b0cf68af01f4535e60eeb38b9a8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871525"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a>Der Name "\<namespacename>" im Stammnamespace "\<fullnamespacename>" ist nicht CLS-kompatibel.

Eine Assembly ist als gekennzeichnet `<CLSCompliant(True)>` , aber ein Element des Stamm Namespace namens beginnt mit einem Unterstrich ( `_` ).  
  
 Ein Programmier Element kann ein oder mehrere Unterstriche enthalten, aber damit es mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf es nicht mit einem Unterstrich beginnen. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40039  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie CLS-Konformität benötigen, ändern Sie den Stamm Namespace Namen, damit keines seiner Elemente mit einem Unterstrich beginnt.  
  
- Wenn der Namespace Name unverändert bleiben muss, entfernen Sie das <xref:System.CLSCompliantAttribute> aus der Assembly, oder markieren Sie es als `<CLSCompliant(False)>` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Namespace-Anweisung](../statements/namespace-statement.md)
- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [-rootnamespace](../../reference/command-line-compiler/rootnamespace.md)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Benennungskonventionen in Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
