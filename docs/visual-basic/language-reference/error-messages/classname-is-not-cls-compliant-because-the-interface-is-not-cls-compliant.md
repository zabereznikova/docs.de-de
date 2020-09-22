---
title: <classname> ist nicht CLS-kompatibel, da die <interfacename>-Schnittstelle, von der geerbt wird, nicht CLS-kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: a482d14094a3fa86b56ca84af46c45e6093416c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874628"
---
# <a name="classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a>\<classname> ist nicht CLS-kompatibel, da die \<interfacename>-Schnittstelle, von der geerbt wird, nicht CLS-kompatibel ist

Eine Klasse oder Schnittstelle wird als `<CLSCompliant(True)>` gekennzeichnet, wenn sie von einem Typ abgeleitet ist oder einen Typ implementiert, der als `<CLSCompliant(False)>` oder gar nicht gekennzeichnet ist.  
  
 Damit eine Klasse oder Schnittstelle mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, muss die gesamte Vererbungs Hierarchie kompatibel sein. Das bedeutet, dass jeder Typ, von dem sie direkt oder indirekt erbt, kompatibel sein muss. Analog dazu muss eine Klasse, wenn sie eine oder mehrere Schnittstellen implementiert, deren Kompatibilität durch alle Vererbungshierarchien sicherstellen.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40029  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie CLS-Kompatibilität benötigen, definieren Sie diesen Typ innerhalb einer anderen Vererbungshierarchie oder eines anderen Implementierungsschemas.  
  
- Wenn dieser Typ in der aktuellen Vererbungshierarchie oder dem aktuellen Implementierungsschema verbleiben muss, entfernen Sie das <xref:System.CLSCompliantAttribute> aus seiner Definition, oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.  
