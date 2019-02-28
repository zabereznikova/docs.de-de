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
ms.openlocfilehash: b8dfc166681dbadf1d2f4ba5a985011f5427f50a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981425"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Stellt den Standardwert eines beliebigen Datentyps dar. Für Verweistypen; der Standardwert ist die `null` Verweis. Der Standardwert hängt für Werttypen gibt an, ob der Werttyp auf NULL festlegbar ist.  
  
> [!NOTE]
>  Für nicht auf NULL festlegbare Werttypen `Nothing` in Visual Basic unterscheidet sich von `null` in C#. In Visual Basic, wenn Sie festlegen, dass eine Variable eines Typs NULL-Werte in `Nothing`, die Variable auf den Standardwert für den deklarierten Typ festgelegt ist. In C#, wenn Sie eine Variable eines Typs NULL-Werte in zuweisen `null`, ein Fehler während der Kompilierung auftritt.  
  
## <a name="remarks"></a>Hinweise  
 `Nothing` Stellt den Standardwert eines Datentyps dar. Der Standardwert hängt davon ab, ob die Variable ein Werttyp oder ein Verweistyp ist.  
  
 Eine Variable ein *Werttyp* den Wert enthält. Werttypen gehören alle numerischen Datentypen `Boolean`, `Char`, `Date`, werden alle vorhandenen Strukturen und alle Enumerationen. Eine Variable ein *Verweistyp* speichert einen Verweis auf eine Instanz des Objekts im Arbeitsspeicher. Verweistypen umfassen Klassen, Arrays, Zeichenfolgen und Delegaten. Weitere Informationen finden Sie unter [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Wenn eine Variable eines Werts eingeben, wird das Verhalten der `Nothing` abhängig, ob die Variable von einem NULL-Werte zulässt. Zur Darstellung von NULL-Werte zulassen, Hinzufügen einer `?` Modifizierer auf den Namen fest. Zuweisen von `Nothing` setzt Sie den Wert einer Variablen auf NULL festlegbare auf `null`. Weitere Informationen und Beispiele finden Sie unter [auf NULL festlegbare Werttypen](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Wenn eine Variable eines Werttyps, der nicht NULL sein kann, Zuweisen von `Nothing` , wird es auf den Standardwert für den deklarierten Typ. Wenn dieses Typs Variable Membern enthält, können sie auf ihre Standardwerte zurück. Das folgende Beispiel zeigt dies für skalare Typen.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Wenn eine Variable eines Referenztyps, Zuweisen von `Nothing` auf die Variable wird auf eine `null` Verweis, der den Typ der Variablen. Eine Variable, die festgelegt wird, um eine `null` Verweis ist nicht mit einem beliebigen Objekt verknüpft. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 Wenn Sie, ob ein Verweis (oder geben Sie NULL-Wert) überprüfen Variable ist `null`, verwenden Sie keine `= Nothing` oder `<> Nothing`. Verwenden Sie immer `Is Nothing` oder `IsNot Nothing`.  
  
 Für Zeichenfolgen in Visual Basic, der leeren Zeichenfolge entspricht `Nothing`. Aus diesem Grund `"" = Nothing` ist "true".  
  
 Das folgende Beispiel zeigt, vergleichen, verwenden die `Is` und `IsNot` Operatoren.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Wenn Sie eine Variable, ohne deklarieren eine `As` Klausel und legen ihn auf `Nothing`, hat die Variable ein `Object`. Ein Beispiel hierfür ist `Dim something = Nothing`. Ein Fehler während der Kompilierung tritt in diesem Fall auf, wenn `Option Strict` befindet sich auf und `Option Infer` ist deaktiviert.  
  
 Wenn Sie zuweisen, `Nothing` einer Objektvariablen, es nicht mehr bezieht sich auf eine Objektinstanz. Wenn die Variable an eine Instanz bereits verwiesen hat, wenn diese Option auf `Nothing` wird die Instanz selbst nicht beendet. Die Instanz beendet ist, und der Speicher und Systemressourcen zugeordnet sind, erst freigegeben, nachdem der Garbage Collector (GC) feststellt, dass es keine aktiven Verweise mehr.  
  
 `Nothing` unterscheidet sich von der <xref:System.DBNull> Objekt, das eine nicht initialisierte Variante oder eine Spalte nicht vorhandene Datenbank darstellt.  
  
## <a name="see-also"></a>Siehe auch
- [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)
- [Objektlebensdauer: Wie die Objekte erstellt und zerstört werden](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Lebensdauer in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Is-Operator](../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Auf NULL festlegbare Werttypen](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
