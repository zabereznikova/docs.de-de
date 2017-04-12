---
title: '&quot;&lt;Classname&gt;&quot;ist nicht CLS-kompatibel, da die Schnittstelle&quot;&lt;Interfacename&gt;&quot; Es implementiert ist nicht CLS-kompatibel. | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
dev_langs:
- VB
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 1e5c948ed5ddeaa2f8a8efd4aa83a2539cc862f3
ms.lasthandoff: 03/13/2017

---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a>'&lt;Classname&gt;"ist nicht CLS-kompatibel, da die Schnittstelle"&lt;Interfacename&gt;' Es implementiert ist nicht CLS-kompatibel.
Eine Klasse oder Schnittstelle wird als `<CLSCompliant(True)>` gekennzeichnet, wenn sie von einem Typ abgeleitet ist oder einen Typ implementiert, der als `<CLSCompliant(False)>` oder gar nicht gekennzeichnet ist.  
  
 Für eine Klasse oder Schnittstelle, um die Kompatibilität mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), ihre gesamte Vererbungshierarchie kompatibel sein. Das bedeutet, dass jeder Typ, von dem sie direkt oder indirekt erbt, kompatibel sein muss. Analog dazu muss eine Klasse, wenn sie eine oder mehrere Schnittstellen implementiert, deren Konformität durch alle Vererbungshierarchien sicherstellen.  
  
 Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute> Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute>  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40029  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie CLS-Konformität benötigen, definieren Sie diesen Typ innerhalb einer anderen Vererbungshierarchie oder eines anderen Implementierungsschemas.  
  
-   Wenn dieser Typ innerhalb der aktuellen Vererbung oder Schema verbleiben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Definition oder markieren Sie ihn als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>Siehe auch  
 [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
