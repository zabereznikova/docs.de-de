---
title: Der zugrunde liegende <typename>-Typ der Enumeration ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 7d4566637da74726867c55ddf89b965d055e5d14
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589918"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a>Der zugrunde liegende Typ \<Typename > der Enumeration ist nicht CLS-kompatibel.
Der Datentyp angegeben werden, für diese Enumeration nicht ist Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Dies ist ein Fehler in der Komponente, nicht auf, weil die .NET Framework und Visual Basic diesen Datentyp unterstützt. Allerdings kann in eine andere Komponente, die in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt. Eine solche Komponente möglicherweise nicht erfolgreich mit der Komponente interagieren können.  
  
 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:  
  
- [SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC40032  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn die Komponente nur mit anderen Komponenten von .NET Framework-Schnittstellen oder nicht mit anderen Komponenten verbunden ist, müssen Sie keine Änderungen vornehmen.  
  
- Wenn mit einer Komponente, die nicht für .NET Framework geschrieben wurden verbunden sind, können Sie über Reflektion oder in der Dokumentation, um zu bestimmen können, ob dieser Datentyp unterstützt. Wenn dies der Fall ist, müssen Sie keine Änderungen vornehmen.  
  
- Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie es mit den ähnlichsten CLS-kompatiblen Typ ersetzen. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.  
  
- Wenn Sie mit Automatisierungs- oder COM-Objekten verbunden ist, Bedenken Sie, dass einige Typen in .NET Framework über andere Datenbreiten als verfügen. Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UShort` anstelle von `UInteger` in verwaltetem Visual Basic-Code.  
  
## <a name="see-also"></a>Siehe auch

- [Reflektion (Visual Basic)](../../programming-guide/concepts/reflection.md)
- [Reflexion](../../../framework/reflection-and-codedom/reflection.md)
