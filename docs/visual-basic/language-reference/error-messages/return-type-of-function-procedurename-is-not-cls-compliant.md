---
title: "Der Rückgabetyp der Funktion &#39; &lt;Prozedurname&gt;&#39; ist nicht CLS-kompatibel."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords: BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16670521ec09ae9cab28bf6ca4705c131fd84701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>Der Rückgabetyp der Funktion &#39; &lt;Prozedurname&gt;&#39; ist nicht CLS-kompatibel.
Ein `Function` Prozedur RuntimeCompatibility als `<CLSCompliant(True)>` gibt jedoch einen Typ mit der Kennzeichnung `<CLSCompliant(False)>`, nicht markiert ist oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.  
  
 Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden. Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.  
  
 Die folgenden [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Datentypen sind nicht CLS-kompatibel:  
  
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
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie eine 16-Bit-Ganzzahl an eine solche Komponente zurückgeben, deklarieren Sie es als `Short` anstelle von `Integer` im verwalteten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Code.  
  
## <a name="see-also"></a>Siehe auch  
 [\<PAVE über > Schreiben von CLS-kompatiblem Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
