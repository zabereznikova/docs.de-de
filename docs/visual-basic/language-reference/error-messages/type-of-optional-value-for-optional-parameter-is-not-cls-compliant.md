---
title: Der Typ des optionalen Werts für den optionalen <parametername>-Parameter ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 88f8b7ea1e0a9b4cb115646f40abbf8a567a2b1d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641388"
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
  
- Wenn Sie mit Automatisierungs- oder COM-Objekten verbunden ist, Bedenken Sie, dass einige Typen in .NET Framework über andere Datenbreiten als verfügen. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie eine 16-Bit-Ganzzahl in eine solche Komponente akzeptieren, deklarieren Sie sie als `Short` anstelle von `Integer` in verwaltetem Visual Basic-Code.
