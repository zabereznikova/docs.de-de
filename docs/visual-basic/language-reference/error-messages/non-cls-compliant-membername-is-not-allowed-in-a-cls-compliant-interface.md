---
title: "Nicht CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle unzulässig | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2861ef22c9307e5bd7d2eabf4f6e37bbd9086345
ms.lasthandoff: 03/13/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Nicht CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle nicht zulässig
Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer Schnittstelle ist als markiert `<CLSCompliant(True)>` Wenn die Schnittstelle selbst markiert ist, als `<CLSCompliant(False)>` oder gar nicht markiert ist.  
  
 Für eine Schnittstelle, kompatibel mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), alle seine Member müssen kompatibel sein.  
  
 Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement, legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute> Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute>  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40033  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie CLS-Kompatibilität erfordert und haben die Kontrolle über den Quellcode für die Schnittstelle, markieren Sie die Schnittstelle als `<CLSCompliant(True)>` Wenn alle seine Member kompatibel sind.  
  
-   Definieren Sie Wenn Sie CLS-Kompatibilität erfordert und haben keine Kontrolle über den Quellcode für die Schnittstelle oder nicht qualifiziert wird, kompatibel ist, dieser Member innerhalb einer anderen Schnittstelle.  
  
-   Wenn Sie dieses Element in der aktuellen Schnittstelle verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Definition oder markieren Sie ihn als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>Siehe auch  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
