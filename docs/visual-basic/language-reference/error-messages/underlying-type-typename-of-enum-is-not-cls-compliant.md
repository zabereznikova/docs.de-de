---
title: Zugrunde liegender Typ &lt;Typename&gt; Enumeration ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44727a60f99e0d00cde7d569e2017928551b1812
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a>Zugrunde liegender Typ &lt;Typename&gt; Enumeration ist nicht CLS-kompatibel.
Der Datentyp für die angegebene diese Enumeration nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Dies ist kein Fehler innerhalb der Komponente, da die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] und Visual Basic unterstützt diesen Datentyp. Allerdings kann eine andere Komponente in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt. Eine solche Komponente kann möglicherweise nicht erfolgreich mit der Komponente interagieren.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
-   [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40032  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Komponenten oder nicht mit anderen Komponenten verbunden, müssen Sie nicht nichts ändern.  
  
-   Wenn Sie eine Komponente, die nicht für geschriebenen Datenbreite der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], um zu bestimmen, entweder über Reflektion können Sie möglicherweise oder aus der Dokumentation gibt an, ob sie diesen Datentyp unterstützt. Wenn dies der Fall ist, müssen Sie nicht ändert nichts.  
  
-   Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie ihn durch den ähnlichsten CLS-kompatiblen Typ ersetzen. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
-   Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen. Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` im verwalteten Visual Basic-Code.  
  
## <a name="see-also"></a>Siehe auch  
 [Reflektion (Visual Basic)](../../programming-guide/concepts/reflection.md)  
 [Reflexion](../../../framework/reflection-and-codedom/reflection.md)  
 
