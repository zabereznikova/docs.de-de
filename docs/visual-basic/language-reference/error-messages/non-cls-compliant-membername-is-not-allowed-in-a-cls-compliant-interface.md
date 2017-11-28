---
title: "Nicht CLS-kompatible &lt;Membername&gt; ist in einem CLS-kompatible Schnittstelle nicht zulässig"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 358abd338d3ce780c2f0aae7aa8efb53e57b477c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Nicht CLS-kompatible &lt;Membername&gt; ist in einem CLS-kompatible Schnittstelle nicht zulässig
Einer Eigenschaft, Prozedur oder einem Ereignis in einer Schnittstelle ist als gekennzeichnet `<CLSCompliant(True)>` Wenn die Schnittstelle selbst markiert ist, als `<CLSCompliant(False)>` oder überhaupt nicht gekennzeichnet.  
  
 Für eine Schnittstelle einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), alle seine Member müssen kompatibel sein.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40033  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie CLS-Kompatibilität benötigen und Kontrolle über den Quellcode der Schnittstelle haben, markieren Sie die Schnittstelle als `<CLSCompliant(True)>` Wenn allen zugehörigen Membern kompatibel sind.  
  
-   Definieren Sie Wenn Sie CLS-Kompatibilität benötigen und haben keine Kontrolle über den Quellcode für die Schnittstelle oder nicht qualifiziert wird, kompatibel sein müssen, den Member innerhalb einer anderen Schnittstelle.  
  
-   Wenn Sie dieses Element in der aktuellen Schnittstelle verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Siehe auch  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [\<PAVE über > Schreiben von CLS-kompatiblem Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
