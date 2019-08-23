---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963762"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Stellt den Standardwert eines beliebigen Datentyps dar. Bei Verweis Typen ist der Standardwert der `null` Verweis. Für Werttypen hängt der Standardwert davon ab, ob der Werttyp NULL-Werte zulässt.  
  
> [!NOTE]
> Bei nicht auf NULL festleg baren Werttypen unterscheidet `Nothing` sich C#in Visual Basic von `null` in. Wenn Sie in Visual Basic eine Variable eines Werttyps, der keine NULL-Werte `Nothing`zulässt, auf festlegen, wird die Variable auf den Standardwert für den deklarierten Typ festgelegt. Wenn C#Sie in eine Variable eines Werttyps, der keine NULL-Werte `null`zulässt, auf zuweisen, tritt ein Kompilierzeitfehler auf.  
  
## <a name="remarks"></a>Hinweise  
 `Nothing`stellt den Standardwert eines-Datentyps dar. Der Standardwert hängt davon ab, ob es sich bei der Variablen um einen Werttyp oder einen Verweistyp handelt.  
  
 Eine Variable eines *Werttyps* enthält direkt den zugehörigen Wert. Zu den Werttypen zählen alle numerischen `Boolean`Daten `Char`Typen `Date`,,,, alle Strukturen und alle Enumerationen. Eine Variable eines *Verweis Typs* speichert einen Verweis auf eine Instanz des Objekts im Arbeitsspeicher. Verweis Typen umfassen Klassen, Arrays, Delegaten und Zeichen folgen. Weitere Informationen finden Sie unter [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Wenn eine Variable einen Werttyp hat, hängt das Verhalten `Nothing` von davon ab, ob die Variable einen Datentyp hat, der NULL-Werte zulässt. Um einen Werttyp anzugeben, der NULL- `?` Werte zulässt, fügen Sie dem Typnamen einen Modifizierer hinzu. Beim `Nothing` zuweisen zu einer Variablen, die NULL zulässt, `null`wird der Wert auf festgelegt Weitere Informationen und Beispiele finden Sie unter [Nullable-Werttypen](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Wenn eine Variable einen Werttyp hat, der nicht auf NULL festgelegt `Nothing` werden kann, wird Sie durch Zuweisen von auf den Standardwert für den deklarierten Typ festgelegt. Wenn dieser Typ Variablen Elemente enthält, werden Sie alle auf ihre Standardwerte festgelegt. Dies wird im folgenden Beispiel für skalare Typen veranschaulicht.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Wenn eine Variable einen Verweistyp hat, wird Sie `Nothing` durch Zuweisen zur Variablen auf einen `null` Verweis auf den Typ der Variablen festgelegt. Eine Variable, die auf einen `null` Verweis festgelegt ist, ist keinem Objekt zugeordnet. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 Wenn Sie überprüfen, ob ein Verweis (oder ein Werttyp `null`, der NULL- `= Nothing` Werte `<> Nothing`zulässt) ist, verwenden Sie nicht oder. Verwenden `Is Nothing` Sie immer `IsNot Nothing`oder.  
  
 Für Zeichen folgen in Visual Basic ist die leere Zeichen `Nothing`Folge. `"" = Nothing` Daher ist true.  
  
 Das folgende Beispiel zeigt Vergleiche, die die `Is` Operatoren und `IsNot` verwenden.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Wenn Sie eine Variable deklarieren, ohne `As` eine-Klausel zu verwenden `Nothing`und diese auf festzulegen, hat `Object`die Variable den Typ. Ein Beispiel hierfür ist `Dim something = Nothing`. In diesem Fall tritt ein Kompilierzeitfehler auf `Option Strict` , wenn auf `Option Infer` on und Off ist.  
  
 Wenn Sie einer `Nothing` Objektvariablen zuweisen, bezieht sie sich nicht mehr auf eine Objektinstanz. Wenn die Variable zuvor auf eine Instanz verwiesen hat, wird die Instanz `Nothing` selbst nicht beendet, wenn Sie auf festgelegt ist. Die Instanz wird beendet, und die zugeordneten Arbeitsspeicher-und Systemressourcen werden erst freigegeben, nachdem die Garbage Collector (GC) erkannt hat, dass noch keine aktiven Verweise vorhanden sind.  
  
 `Nothing`unterscheidet sich <xref:System.DBNull> von dem-Objekt, das eine nicht initialisierte Variante oder eine nicht vorhandene Daten Bank Spalte darstellt.  
  
## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)
- [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Lebensdauer in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Is-Operator](../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Auf NULL festlegbare Werttypen](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
