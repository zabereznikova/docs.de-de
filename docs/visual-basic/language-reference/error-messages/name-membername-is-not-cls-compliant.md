---
title: Namen &lt;Membername&gt; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords: BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7f574c2ebd71dbe06c4a687728e7812a18c8a949
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Namen &lt;Membername&gt; ist nicht CLS-kompatibel.
Eine Assembly ist als markiert `<CLSCompliant(True)>` aber macht ein Element mit einem Namen, die mit einem Unterstrich beginnt (`_`).  
  
 Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch werden zum Einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), es muss nicht mit einem Unterstrich beginnen. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40031  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Membernamen, damit er nicht mit einem Unterstrich beginnt.  
  
-   Wenn Sie festlegen, dass es sich bei der Membernamen unverändert bleiben, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`. Sie können weiterhin die Assembly als kennzeichnen `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>Siehe auch  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [\<PAVE über > Schreiben von CLS-kompatiblem Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
