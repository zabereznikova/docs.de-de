---
title: Der Typ des Members "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: c8c14a2d6df8804967807af881384bc7d9ccd99f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163479"
---
# <a name="bc40025-type-of-member-membername-is-not-cls-compliant"></a>BC40025: der Typ des Members " \<membername> " ist nicht CLS-kompatibel.

Der für diesen Member angegebene Datentyp ist nicht Teil der [Sprachunabhängigkeit und der Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Dies ist kein Fehler in der Komponente, da der .NET Framework und Visual Basic diesen Datentyp unterstützen. Eine andere Komponente, die in streng CLS-kompatibler Code geschrieben wird, unterstützt diesen Datentyp jedoch möglicherweise nicht. Eine solche Komponente ist möglicherweise nicht in der Lage, mit Ihrer Komponente erfolgreich zu interagieren.

 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:

- [SByte-Datentyp](../data-types/sbyte-data-type.md)

- [UInteger-Datentyp](../data-types/uinteger-data-type.md)

- [ULong-Datentyp](../data-types/ulong-data-type.md)

- [UShort-Datentyp](../data-types/ushort-data-type.md)

 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC40025

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn sich die Komponente nur mit anderen .NET Framework Komponenten oder nicht mit anderen Komponenten verbinden lässt, müssen Sie nichts ändern.

- Wenn Sie mit einer Komponente verbunden sind, die nicht für die .NET Framework geschrieben wurde, können Sie möglicherweise entweder durch Reflektion oder aus der Dokumentation ermitteln, ob dieser Datentyp unterstützt wird. Wenn dies der Fall ist, müssen Sie nichts ändern.

- Wenn Sie mit einer Komponente interagieren, die diesen Datentyp nicht unterstützt, müssen Sie Sie durch den nächstgelegenen CLS-kompatiblen Typ ersetzen. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.

- Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework. Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` in Ihrem verwalteten Visual Basic-Code.

## <a name="see-also"></a>Siehe auch

- [Reflexion](../../../framework/reflection-and-codedom/reflection.md)
