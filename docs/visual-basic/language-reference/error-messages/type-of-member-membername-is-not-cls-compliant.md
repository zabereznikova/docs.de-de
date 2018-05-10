---
title: Typ des Elements &#39; &lt;Membername&gt; &#39; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 5735b5104884a702a649a029116be7446424ec67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>Typ des Elements &#39; &lt;Membername&gt; &#39; ist nicht CLS-kompatibel.
Den Datentyp für die angegebene bei diesem Member nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Dies ist kein Fehler innerhalb der Komponente, da die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] und Visual Basic unterstützt diesen Datentyp. Allerdings kann eine andere Komponente in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt. Eine solche Komponente kann möglicherweise nicht erfolgreich mit der Komponente interagieren.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Komponenten oder nicht mit anderen Komponenten verbunden, müssen Sie nicht nichts ändern.  
  
-   Wenn Sie eine Komponente, die nicht für geschriebenen Datenbreite der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], um zu bestimmen, entweder über Reflektion können Sie möglicherweise oder aus der Dokumentation gibt an, ob sie diesen Datentyp unterstützt. Wenn dies der Fall ist, müssen Sie nicht ändert nichts.  
  
-   Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie ihn durch den ähnlichsten CLS-kompatiblen Typ ersetzen. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` im verwalteten Visual Basic-Code.  
  
## <a name="see-also"></a>Siehe auch  
 [Reflexion](../../../framework/reflection-and-codedom/reflection.md)  
 
