---
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 88d609146648fe1b0c3124b99a65e85293fc0707
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406429"
---
# <a name="ctype-function-visual-basic"></a>CType-Funktion (Visual Basic)

Gibt das Ergebnis einer expliziten Konvertierung eines Ausdrucks in einen angegebenen Datentyp, ein Objekt, eine Struktur, Klasse oder Schnittstelle zurück.

## <a name="syntax"></a>Syntax

```vb
CType(expression, typename)
```

## <a name="parts"></a>Bestandteile

`expression`Ein beliebiger gültiger Ausdruck. Wenn der Wert von `expression` außerhalb des von `typename` definierten Bereichs liegt, wird von Visual Basic eine Ausnahme ausgelöst.

`typename`Jeder Ausdruck, der innerhalb einer- `As` Klausel in einer-Anweisung zulässig ist `Dim` , d. h. der Name eines beliebigen Datentyps, eines Objekts, einer Struktur, Klasse oder Schnittstelle.

## <a name="remarks"></a>Bemerkungen

> [!TIP]
> Sie können die folgenden Funktionen auch zum Ausführen einer Typkonvertierung verwenden:
>
> - Typkonvertierungsfunktionen, wie `CByte`, `CDbl` und `CInt`, mit denen eine Konvertierung in einen bestimmten Datentyp ausgeführt werden kann. Weitere Informationen finden Sie unter [Funktionen für die Typkonvertierung](type-conversion-functions.md).
> - [DirectCast-Operator](../operators/directcast-operator.md) oder [TryCast-Operator](../operators/trycast-operator.md). Diese Operatoren erfordern, dass ein Typ von dem Anderen erbt oder diesen implementiert. Sie können etwas bessere Leistung beim Konvertieren in und aus dem `CType`-Datentyp bieten, als `Object`.

`CType` wird inline kompiliert. Das bedeutet, dass der Konvertierungscode Bestandteil des Codes für die Auswertung des Ausdrucks ist. In einigen Fällen wird der Code schneller ausgeführt, da keine Prozeduren zum Ausführen der Konvertierung aufgerufen werden.

Wenn keine Konvertierung von `expression` in `typename` (zum Beispiel von `Integer` in `Date`) definiert ist, wird von Visual Basic zur Kompilierungszeit eine Fehlermeldung angezeigt.

Falls eine Konvertierung zur Laufzeit fehlschlägt, wird die entsprechende Ausnahme ausgelöst. Ist eine einschränkende Konvertierung fehlerhaft, wird meist ein <xref:System.OverflowException>-Fehler verursacht. Wenn die Konvertierung nicht definiert ist, wird eine <xref:System.InvalidCastException> ausgelöst. Dies kann z. B. der Fall sein, wenn `expression` vom Typ `Object` ist und für seinen Laufzeittyp keine Konvertierung in `typename` definiert ist.

Handelt es sich beim Datentyp von `expression` oder `typename` um eine von Ihnen definierte Klasse oder Struktur, können Sie `CType` für diese Klasse oder Struktur als Konvertierungsoperator definieren. Dadurch wird `CType` als *überladener Operator*fungiert. Wenn Sie einen Konvertierungsoperator definieren, können Sie nicht nur das Verhalten von Konvertierungen in und aus der Klasse oder Struktur steuern, sondern auch die ausgelösten Ausnahmen bestimmen.

## <a name="overloading"></a>Überladen

Der Operator `CType` kann auch für eine Klasse oder Struktur überladen werden, die außerhalb des Codes definiert ist. Wenn in dem Code Konvertierungen in eine solche Klasse oder Struktur oder in umgekehrter Richtung durchführt werden, müssen Sie sicherstellen, dass Sie das Verhalten des betreffenden `CType`-Operators verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Konvertieren von dynamischen Objekten

Typkonvertierungen für dynamische Objekte werden durch benutzerdefinierte dynamische Konvertierungen ausgeführt, bei denen die <xref:System.Dynamic.DynamicObject.TryConvert%2A>-Methode oder die <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>-Methode verwendet werden. Wenn Sie mit dynamischen Objekten arbeiten, verwenden Sie zum Konvertieren des dynamischen Objekts die <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A>-Methode.

## <a name="example"></a>Beispiel

In diesem Beispiel wird die `CType`-Funktion zum Konvertieren eines Ausdrucks in den `Single`-Datentyp verwendet.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Weitere Beispiele finden Sie unter [implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Type Conversion Functions](type-conversion-functions.md)
- [Konvertierungsfunktionen](conversion-functions.md)
- [Operator Statement](../statements/operator-statement.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Typkonvertierung in .NET Framework](../../../standard/base-types/type-conversion.md)
