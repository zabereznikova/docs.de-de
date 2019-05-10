---
title: Der Typ des optionalen Werts für den optionalen <parametername>-Parameter ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: ee7d208f7a579f81690ffbda265bde29316e4ec3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664303"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a>Typ des optionalen Werts für den optionalen Parameter \<Parametername > ist nicht CLS-kompatibel.
Eine Prozedur wird durch `<CLSCompliant(True)>` gekennzeichnet, deklariert jedoch einen [optionalen](../../../visual-basic/language-reference/modifiers/optional.md) Parameter mit dem Standardwert eines nicht kompatiblen Typs.  
  
 Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden. Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen. Dies gilt auch für die Standardwerte der optionalen Parameter.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
- [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> -Attribut auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40042  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn der optionale Parameter einen Standardwert dieses bestimmten Typs verfügen muss, entfernen Sie <xref:System.CLSCompliantAttribute>. Die Prozedur kann nicht CLS-kompatibel sein.  
  
- Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ des Standardwerts in den ähnlichsten CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
- Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie eine 16-Bit-Ganzzahl in eine solche Komponente akzeptieren, deklarieren Sie sie als `Short` anstelle von `Integer` in verwaltetem Visual Basic-Code.