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
ms.openlocfilehash: 18b2d5a28cd6ef885ba8d237da6764dbbd108b59
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348100"
---
# <a name="ctype-function-visual-basic"></a>CType-Funktion (Visual Basic)

Gibt das Ergebnis einer expliziten Konvertierung eines Ausdrucks in einen angegebenen Datentyp, ein Objekt, eine Struktur, Klasse oder Schnittstelle zurück.

## <a name="syntax"></a>Syntax

```vb
CType(expression, typename)
```

## <a name="parts"></a>-Komponenten

`expression` einen beliebigen gültigen Ausdruck. Wenn der Wert von `expression` außerhalb des von `typename` definierten Bereichs liegt, wird von Visual Basic eine Ausnahme ausgelöst.

`typename` einen beliebigen Ausdruck, der in einer `As`-Klausel in einer `Dim`-Anweisung zulässig ist, d. h. den Namen eines beliebigen Datentyps, Objekts, einer Struktur, Klasse oder Schnittstelle.

## <a name="remarks"></a>Hinweise

> [!TIP]
> Sie können die folgenden Funktionen auch zum Ausführen einer Typkonvertierung verwenden:
>
> - Typkonvertierungsfunktionen, wie `CByte`, `CDbl` und `CInt`, mit denen eine Konvertierung in einen bestimmten Datentyp ausgeführt werden kann. Weitere Informationen finden Sie unter [Typkonvertierungs Funktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).
> - [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md). Diese Operatoren erfordern, dass ein Typ von dem Anderen erbt oder diesen implementiert. Sie können etwas bessere Leistung beim Konvertieren in und aus dem `CType`-Datentyp bieten, als `Object`.

`CType` wird Inline kompiliert. Dies bedeutet, dass der Konvertierungs Code Teil des Codes ist, der den Ausdruck auswertet. In einigen Fällen wird der Code schneller ausgeführt, da keine Prozeduren zum Ausführen der Konvertierung aufgerufen werden.

Wenn keine Konvertierung von `expression` in `typename` (zum Beispiel von `Integer` in `Date`) definiert ist, wird von Visual Basic zur Kompilierungszeit eine Fehlermeldung angezeigt.

Falls eine Konvertierung zur Laufzeit fehlschlägt, wird die entsprechende Ausnahme ausgelöst. Ist eine einschränkende Konvertierung fehlerhaft, wird meist ein <xref:System.OverflowException>-Fehler verursacht. Wenn die Konvertierung nicht definiert ist, wird eine <xref:System.InvalidCastException> ausgelöst. Dies kann z. B. der Fall sein, wenn `expression` vom Typ `Object` ist und für seinen Laufzeittyp keine Konvertierung in `typename` definiert ist.

Handelt es sich beim Datentyp von `expression` oder `typename` um eine von Ihnen definierte Klasse oder Struktur, können Sie `CType` für diese Klasse oder Struktur als Konvertierungsoperator definieren. Dadurch wird `CType` als *überladener Operator*fungieren. Wenn Sie einen Konvertierungsoperator definieren, können Sie nicht nur das Verhalten von Konvertierungen in und aus der Klasse oder Struktur steuern, sondern auch die ausgelösten Ausnahmen bestimmen.

## <a name="overloading"></a>Überladen

Der Operator `CType` kann auch für eine Klasse oder Struktur überladen werden, die außerhalb des Codes definiert ist. Wenn in dem Code Konvertierungen in eine solche Klasse oder Struktur oder in umgekehrter Richtung durchführt werden, müssen Sie sicherstellen, dass Sie das Verhalten des betreffenden `CType`-Operators verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Konvertieren von dynamischen Objekten

Typkonvertierungen für dynamische Objekte werden durch benutzerdefinierte dynamische Konvertierungen ausgeführt, bei denen die <xref:System.Dynamic.DynamicObject.TryConvert%2A>-Methode oder die <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>-Methode verwendet werden. Wenn Sie mit dynamischen Objekten arbeiten, verwenden Sie zum Konvertieren des dynamischen Objekts die <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A>-Methode.

## <a name="example"></a>Beispiel

In diesem Beispiel wird die `CType`-Funktion zum Konvertieren eines Ausdrucks in den `Single`-Datentyp verwendet.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Weitere Beispiele finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierungsfunktionen](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Typkonvertierung in .NET Framework](../../../standard/base-types/type-conversion.md)
