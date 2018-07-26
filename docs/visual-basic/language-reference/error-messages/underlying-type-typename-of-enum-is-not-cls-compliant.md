---
title: Der zugrunde liegende Typ &lt;Typename&gt; der Enumeration ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 876a59d1441c1ba4c5057556d5ef2fb2ecb43af6
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959678"
---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a>Der zugrunde liegende Typ &lt;Typename&gt; der Enumeration ist nicht CLS-kompatibel.
Der Datentyp angegeben werden, für diese Enumeration nicht ist Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Dies ist kein Fehler in der Komponente, da die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] und Visual Basic unterstützt diesen Datentyp. Allerdings kann in eine andere Komponente, die in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt. Eine solche Komponente möglicherweise nicht erfolgreich mit der Komponente interagieren können.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen aus, oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40032  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Komponenten oder nicht mit anderen Komponenten verbunden, Sie müssen keine Änderungen vornehmen.  
  
-   Wenn Sie mit einer Komponente, die nicht für geschriebenen anbinden, müssen die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], Sie möglicherweise fest, über Reflektion oder anhand der Dokumentation gibt an, ob sie diesen Datentyp unterstützt. Wenn dies der Fall ist, müssen Sie keine Änderungen vornehmen.  
  
-   Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie es mit den ähnlichsten CLS-kompatiblen Typ ersetzen. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UShort` anstelle von `UInteger` in verwaltetem Visual Basic-Code.  
  
## <a name="see-also"></a>Siehe auch  
 [Reflektion (Visual Basic)](../../programming-guide/concepts/reflection.md)  
 [Reflexion](../../../framework/reflection-and-codedom/reflection.md)  
 
