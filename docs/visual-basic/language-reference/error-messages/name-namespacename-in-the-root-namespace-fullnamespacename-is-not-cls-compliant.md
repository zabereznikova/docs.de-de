---
title: Namen &lt;Namespacename&gt; im Stammnamespace &lt;Fullnamespacename&gt; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 8d35268891711ca7f2a7f5ec47be425e342dccd7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642528"
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a>Namen &lt;Namespacename&gt; im Stammnamespace &lt;Fullnamespacename&gt; ist nicht CLS-kompatibel.
Eine Assembly ist als markiert `<CLSCompliant(True)>`, aber ein Element von der stammnamespacename beginnt mit einem Unterstrich (`_`).  
  
 Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, jedoch werden zur Einhaltung der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), es muss nicht mit einem Unterstrich beginnen. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40039  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie CLS-Kompatibilität benötigen, ändern Sie den Stammnamespace-Name, sodass keines ihrer Elemente mit einem Unterstrich beginnt.  
  
-   Wenn Sie benötigen, dass der Namespacename unverändert bleiben, entfernen Sie die <xref:System.CLSCompliantAttribute> aus der Assembly oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Siehe auch
- [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

