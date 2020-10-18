---
title: Der Rückgabetyp der <procedurename>-Funktion ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 9a877046a1b30e2e3773a41b8b44573e11ff1c96
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159702"
---
# <a name="bc40027-return-type-of-function-procedurename-is-not-cls-compliant"></a>BC40027: der Rückgabetyp der Funktion "" \<procedurename> ist nicht CLS-kompatibel.

Eine `Function` Prozedur ist als gekennzeichnet, `<CLSCompliant(True)>` gibt jedoch einen Typ zurück, der als markiert ist `<CLSCompliant(False)>` , nicht markiert ist oder nicht qualifiziert ist, weil es sich um einen nicht kompatiblen Typ handelt.

 Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden. Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.

 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:

- [SByte-Datentyp](../data-types/sbyte-data-type.md)

- [UInteger-Datentyp](../data-types/uinteger-data-type.md)

- [ULong-Datentyp](../data-types/ulong-data-type.md)

- [UShort-Datentyp](../data-types/ushort-data-type.md)

 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.

 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.

 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC40027

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn die `Function` Prozedur diesen bestimmten Typ zurückgeben muss, entfernen Sie den <xref:System.CLSCompliantAttribute> . Die Prozedur kann nicht CLS-kompatibel sein.

- Wenn die `Function` Prozedur CLS-kompatibel sein muss, ändern Sie den Rückgabetyp in den nächstgelegenen CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.

- Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie eine 16-Bit-Ganzzahl an eine solche Komponente zurückgeben, deklarieren Sie Sie als `Short` anstelle von `Integer` in Ihrem verwalteten Visual Basic-Code.
