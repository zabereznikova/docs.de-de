---
title: Namen &lt;Membername&gt; ist nicht CLS-kompatibel. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
dev_langs:
- VB
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
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
ms.openlocfilehash: 6a678c66580a7917a3869aac81418152130debff
ms.lasthandoff: 03/13/2017

---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Namen &lt;Membername&gt; ist nicht CLS-kompatibel.
Eine Assembly ist als markiert `<CLSCompliant(True)>` macht ein Element mit einem Namen, die mit einem Unterstrich beginnt jedoch (`_`).  
  
 Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch zum kompatibel sein, mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), es muss nicht mit einem Unterstrich beginnen. Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute> Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute>  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40031  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie die Kontrolle über den Quellcode verfügen, ändern Sie den Membernamen, damit er nicht mit einem Unterstrich beginnt.  
  
-   Wenn der Elementname unverändert bleiben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Definition oder markieren Sie ihn als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute> Sie können weiterhin markieren Sie die Assembly als `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>Siehe auch  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
