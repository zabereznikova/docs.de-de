---
title: Rückgabetyp der Funktion &#39; &lt;Prozedurname&gt; &#39; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: b7704ee63031c38f708a2243e84b880c25fcf819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595003"
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>Rückgabetyp der Funktion &#39; &lt;Prozedurname&gt; &#39; ist nicht CLS-kompatibel.
Ein `Function` Prozedur RuntimeCompatibility als `<CLSCompliant(True)>` gibt jedoch einen Typ mit der Kennzeichnung `<CLSCompliant(False)>`, nicht markiert ist oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.  
  
 Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden. Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40027  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die `Function` -Prozedur diesen speziellen Typ zurückgeben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>. Die Prozedur kann nicht CLS-kompatibel sein.  
  
-   Wenn die `Function` -Prozedur CLS-kompatibel sein muss, ändern Sie den Rückgabetyp in den ähnlichsten CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie eine 16-Bit-Ganzzahl an eine solche Komponente zurückgeben, deklarieren Sie es als `Short` anstelle von `Integer` im verwalteten Visual Basic-Code.