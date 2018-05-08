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
ms.openlocfilehash: fb1af7d748faac78b26177af453a0e858f9e97c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Stellt den Standardwert eines beliebigen Datentyps dar. Für Verweistypen, der Standardwert ist die `null` Verweis. Der Standardwert hängt für Werttypen gibt an, ob der Werttyp NULL ist.  
  
> [!NOTE]
>  Für Typen mit NULL-Werten `Nothing` in Visual Basic unterscheidet sich vom `null` in C# geschrieben. In Visual Basic, wenn Sie eine Variable eines Typs NULL-Wert für `Nothing`, die Variable wird auf den Standardwert für den deklarierten Typ festgelegt. In C# geschrieben, wenn Sie eine Variable eines Werttyps auf NULL-zuweisen `null`, tritt ein Kompilierzeitfehler auf.  
  
## <a name="remarks"></a>Hinweise  
 `Nothing` Stellt den Standardwert eines Datentyps dar. Der Standardwert hängt davon ab, ob die Variable ein Werttyp oder ein Verweistyp ist.  
  
 Eine Variable vom eine *Werttyp* direkt den Wert enthält. Werttypen gehören alle numerischen Datentypen `Boolean`, `Char`, `Date`, werden alle vorhandenen Strukturen und alle Enumerationen. Eine Variable vom eine *Verweistyp* speichert einen Verweis auf eine Instanz des Objekts im Arbeitsspeicher. Verweistypen enthalten Klassen, Arrays, Delegaten und Zeichenfolgen. Weitere Informationen finden Sie unter [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Geben Sie, wenn eine Variable einen Werttyp handelt, das Verhalten des `Nothing` abhängig, ob die Variable mit einem Datentyp NULL-Werte zulässt. Um einen Werttyp darzustellen, fügen einen `?` Modifizierer dem Typnamen. Zuweisen von `Nothing` auf eine NULL-Werte zulassen Variable wird der Wert auf `null`. Weitere Informationen und Beispiele finden Sie unter [auf NULL festlegbaren Werttypen](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Wenn eine Variable eines Werttyps, die NULL-Werte zulässt ist, Zuweisen von `Nothing` , wird er auf den Standardwert für den deklarierten Typ. Wenn dieses Typs Variablenmember enthält, sind sie bereit, die sich mit ihren Standardwerten. Das folgende Beispiel veranschaulicht dies für skalare Typen.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 Wenn eine Variable eines Verweistyps ist, Zuweisen von `Nothing` auf die Variable wird auf eine `null` Verweis vom Typ der Variablen. Eine Variable, die festgelegt wird, um eine `null` Verweis ist nicht mit jedem Objekt verknüpft. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 Beim Überprüfen von, ob ein Verweis (oder geben Sie NULL-Werte zulassen) des Variable `null`, verwenden Sie keine `= Nothing` oder `<> Nothing`. Verwenden Sie immer `Is Nothing` oder `IsNot Nothing`.  
  
 Für Zeichenfolgen in Visual Basic wird der leeren Zeichenfolge entspricht `Nothing`. Aus diesem Grund `"" = Nothing` ist "true".  
  
 Das folgende Beispiel zeigt vergleichen, verwenden die `Is` und `IsNot` Operatoren.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 Wenn eine Variable zu, ohne deklarieren eine `As` Klausel und legen Sie dafür `Nothing`, hat die Variable einen Typ von `Object`. Ein Beispiel hierfür ist `Dim something = Nothing`. Ein Fehler während der Kompilierung tritt in diesem Fall auf, wenn `Option Strict` befindet sich auf und `Option Infer` ist deaktiviert.  
  
 Wenn Sie zuweisen `Nothing` einer Objektvariablen es nicht mehr bezieht sich auf eine Objektinstanz. Wenn die Variable mit einer Instanz bereits verwiesen hat, eine Festlegung auf `Nothing` wird die Instanz selbst nicht beendet. Die Instanz beendet ist, und der Arbeitsspeicher und Ressourcen zugeordnet werden freigegeben, erst nach der Garbage Collector (GC) erkennt, dass keine aktiven Verweise mehr vorhanden sind.  
  
 `Nothing` unterscheidet sich von der <xref:System.DBNull> Objekt, das eine nicht initialisierte Variante oder eine Spalte nicht vorhandene Datenbank darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Lebensdauer in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Is-Operator](../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot-Operator](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Auf NULL festlegbare Werttypen](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
