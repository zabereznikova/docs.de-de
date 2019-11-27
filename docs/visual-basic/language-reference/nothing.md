---
title: Nothing-Schlüsselwort
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 3bd4681341a33cc8db4ecbc2b284be243db56549
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344164"
---
# <a name="nothing-keyword-visual-basic"></a>Nothing-Schlüsselwort (Visual Basic)

Stellt den Standardwert eines beliebigen Datentyps dar. Der Standardwert für Verweis Typen ist der `null` Verweis. Für Werttypen hängt der Standardwert davon ab, ob der Werttyp NULL-Werte zulässt.

> [!NOTE]
> Bei nicht auf NULL festleg baren Werttypen unterscheiden sich `Nothing` in C#Visual Basic von `null` in. Wenn Sie in Visual Basic eine Variable eines Werttyps, der keine NULL-Werte zulässt, auf `Nothing`festlegen, wird die Variable auf den Standardwert für den deklarierten Typ festgelegt. Wenn C#Sie in eine Variable eines Werttyps, der keine NULL-Werte zulässt, `null`zuweisen, tritt ein Kompilierzeitfehler auf.

## <a name="remarks"></a>Hinweise

`Nothing` stellt den Standardwert eines-Datentyps dar. Der Standardwert hängt davon ab, ob es sich bei der Variablen um einen Werttyp oder einen Verweistyp handelt.

Eine Variable eines *Werttyps* enthält direkt den zugehörigen Wert. Werttypen umfassen alle numerischen Datentypen, `Boolean``Char`, `Date`, alle Strukturen und alle Enumerationen. Eine Variable eines *Verweis Typs* speichert einen Verweis auf eine Instanz des Objekts im Arbeitsspeicher. Verweis Typen umfassen Klassen, Arrays, Delegaten und Zeichen folgen. Weitere Informationen finden Sie unter [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md).

Wenn eine Variable einen Werttyp hat, ist das Verhalten von `Nothing` davon abhängig, ob die Variable einen Datentyp hat, der NULL-Werte zulässt. Um einen Werttyp anzugeben, der NULL-Werte zulässt, fügen Sie dem Typnamen einen `?` Modifizierer hinzu. Durch das Zuweisen von `Nothing` zu einer Variablen, die NULL-Werte zulässt, wird der Wert `null` Weitere Informationen und Beispiele finden Sie unter [Nullable-Werttypen](../programming-guide/language-features/data-types/nullable-value-types.md).

Wenn eine Variable einen Werttyp hat, der nicht auf NULL festgelegt werden kann, wird durch Zuweisen `Nothing` an den Standardwert für den deklarierten Typ festgelegt. Wenn dieser Typ Variablen Elemente enthält, werden Sie alle auf ihre Standardwerte festgelegt. Dies wird im folgenden Beispiel für skalare Typen veranschaulicht.

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

Wenn eine Variable einen Verweistyp hat, wird Sie durch Zuweisen von `Nothing` der Variablen auf einen `null` Verweis auf den Typ der Variablen festgelegt. Eine Variable, die auf einen `null` Verweis festgelegt ist, ist keinem Objekt zugeordnet. Dies wird im folgenden Beispiel veranschaulicht:

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

Wenn Sie überprüfen, ob eine Variable vom Typ Verweis (oder Werte zulässt-Werttyp) `null`ist, verwenden Sie nicht `= Nothing` oder `<> Nothing`. Verwenden Sie immer `Is Nothing` oder `IsNot Nothing`.

Für Zeichen folgen in Visual Basic ist die leere Zeichenfolge `Nothing`. Daher ist `"" = Nothing` "true".

Das folgende Beispiel zeigt Vergleiche, die die Operatoren `Is` und `IsNot` verwenden:

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

Wenn Sie eine Variable deklarieren, ohne eine `As`-Klausel zu verwenden, und Sie auf `Nothing`festlegen, hat die Variable den Typ `Object`. Ein Beispiel hierfür ist `Dim something = Nothing`. In diesem Fall tritt ein Kompilierzeitfehler auf, wenn `Option Strict` auf on und `Option Infer` deaktiviert ist.

Wenn Sie `Nothing` einer Objektvariablen zuweisen, bezieht sie sich nicht mehr auf eine Objektinstanz. Wenn die Variable zuvor auf eine Instanz verwiesen hat, wird die Instanz selbst nicht beendet, wenn Sie auf `Nothing` festgelegt wird. Die Instanz wird beendet, und die zugeordneten Arbeitsspeicher-und Systemressourcen werden erst freigegeben, nachdem die Garbage Collector (GC) erkannt hat, dass noch keine aktiven Verweise vorhanden sind.

`Nothing` unterscheidet sich vom <xref:System.DBNull>-Objekt, das eine nicht initialisierte Variante oder eine nicht vorhandene Daten Bank Spalte darstellt.

## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](./statements/dim-statement.md)
- [Objektlebensdauer: Erstellen und Zerstören von Objekten](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Lebensdauer in Visual Basic](../programming-guide/language-features/declared-elements/lifetime.md)
- [Is-Operator](./operators/is-operator.md)
- [IsNot-Operator](./operators/isnot-operator.md)
- [Auf NULL festlegbare Werttypen](../programming-guide/language-features/data-types/nullable-value-types.md)
