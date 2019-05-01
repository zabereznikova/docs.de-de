---
title: Bestimmen des Objekttyps (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 4014bef2e0c27a0f6a684bc1ed95019f392062a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050518"
---
# <a name="determining-object-type-visual-basic"></a>Bestimmen des Objekttyps (Visual Basic)
Generisches Objektvariablen (d. h. deklarierte Variablen als `Object`) Objekte aus einer Klasse enthalten kann. Bei Verwendung von Variablen des Typs `Object`, müssen Sie möglicherweise verschiedene Aktionen basierend auf der Klasse des Objekts, z. B. einige Objekte können nicht unterstützen, eine bestimmte Eigenschaft oder Methode. Visual Basic bietet zwei Methoden ermitteln, welche Art von Objekt in eine Objektvariable gespeichert ist: die `TypeName` Funktion und die `TypeOf...Is` Operator.  
  
## <a name="typename-and-typeofis"></a>TypeName "und" TypeOf... Ist  
 Die `TypeName` Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, beim Speichern oder Anzeigen der Klassenname des Objekts, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 Die `TypeOf...Is` Operator ist die beste Wahl für den Typ eines Objekts, zu testen, da sie viel schneller als eine entsprechende Zeichenfolge Vergleich ist `TypeName`. Das folgende Codefragment verwendet `TypeOf...Is` innerhalb einer `If...Then...Else` Anweisung:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Hier ist ein Wort der Warnung fällig. Die `TypeOf...Is` Operator gibt `True` wird ein Objekt eines bestimmten Typs ist, oder von einem bestimmten Typ abgeleitet ist. Fast alles, was Visual Basic bieten Ihnen umfasst Objekte, die einige Elemente, die normalerweise nicht betrachtet werden als Objekte, z. B. Zeichenfolgen und Zahlen enthalten. Diese Objekte davon abgeleitet sind, und Methoden erben <xref:System.Object>. Beim Übergeben einer `Integer` und ausgewerteten mit `Object`, die `TypeOf...Is` Operator gibt `True`. Das folgende Beispiel meldet, dass der Parameter `InParam` sowohl eine `Object` und `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 Im folgenden Beispiel wird sowohl `TypeOf...Is` und `TypeName` bestimmen den Typ des Objekts übergeben, die Sie in der `Ctrl` Argument. Die `TestObject` Prozeduraufrufe `ShowType` mit drei verschiedene Arten von Steuerelementen.  
  
#### <a name="to-run-the-example"></a>So führen Sie das Beispiel aus  
  
1. Erstellen Sie ein neues Windows-Anwendungsprojekt und fügen eine <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.CheckBox> -Steuerelement, und ein <xref:System.Windows.Forms.RadioButton> -Steuerelement auf das Formular.  
  
2. Rufen Sie über die Schaltfläche im Formular die `TestObject` Verfahren.  
  
3. Fügen Sie dem Formular den folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [If...Then...Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
