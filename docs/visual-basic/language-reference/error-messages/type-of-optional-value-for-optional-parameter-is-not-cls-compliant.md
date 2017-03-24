---
title: "Typ des optionalen Werts für den optionalen Parameter &lt;Parametername&gt; ist nicht CLS-kompatibel. | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
dev_langs:
- VB
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 8
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
ms.openlocfilehash: 3dbcab01022d1604e79c6bfc3e04a14ef60bc219
ms.lasthandoff: 03/13/2017

---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a>Typ des optionalen Werts für den optionalen Parameter &lt;Parametername&gt; ist nicht CLS-kompatibel.
Eine Prozedur wird durch `<CLSCompliant(True)>` gekennzeichnet, deklariert jedoch einen [optionalen](../../../visual-basic/language-reference/modifiers/optional.md) Parameter mit dem Standardwert eines nicht kompatiblen Typs.  
  
 Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden. Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen. Dies gilt auch für die Standardwerte der optionalen Parameter.  
  
 Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Beim Anwenden der <xref:System.CLSCompliantAttribute>Attribut auf ein Programmierelement legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute> Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie nicht übernehmen <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute>  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40042  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn der optionale Parameter einen Standardwert diesen speziellen Typ aufweisen muss, entfernen Sie <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute> Die Prozedur kann nicht CLS-kompatibel sein.  
  
-   Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ des Standardwerts in den ähnlichsten CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] verfügen. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie von einer solchen Komponente eine 16-Bit-Ganzzahl akzeptieren, deklarieren Sie sie im verwalteten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Code als `Short` anstatt als `Integer`.  
  
## <a name="see-also"></a>Siehe auch  
 [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
