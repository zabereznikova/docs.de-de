---
title: Der Typ des <parametername>-Parameters ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 7043138f770264b73eeac79cd262104b88cd8516
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161230"
---
# <a name="bc40028-type-of-parameter-parametername-is-not-cls-compliant"></a>BC40028: der Typ des Parameters " \<parametername> " ist nicht CLS-kompatibel.

Eine Prozedur ist als gekennzeichnet, `<CLSCompliant(True)>` deklariert jedoch einen Parameter mit einem Typ, der als markiert ist `<CLSCompliant(False)>` , nicht markiert ist oder nicht qualifiziert ist, weil es sich um einen nicht kompatiblen Typ handelt.

 Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden. Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.

 Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:

- [SByte-Datentyp](../data-types/sbyte-data-type.md)

- [UInteger-Datentyp](../data-types/uinteger-data-type.md)

- [ULong-Datentyp](../data-types/ulong-data-type.md)

- [UShort-Datentyp](../data-types/ushort-data-type.md)

 Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben. Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.

 Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.

 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC40028

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn die Prozedur einen Parameter dieses bestimmten Typs annehmen muss, entfernen Sie den <xref:System.CLSCompliantAttribute> . Die Prozedur kann nicht CLS-kompatibel sein.

- Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ dieses Parameters in den nächstgelegenen CLS-kompatiblen Typ. Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen. Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.

- Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework. Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits. Wenn Sie eine 16-Bit-Ganzzahl aus einer solchen Komponente akzeptieren, deklarieren Sie Sie als `Short` anstelle von `Integer` in Ihrem verwalteten Visual Basic-Code.
