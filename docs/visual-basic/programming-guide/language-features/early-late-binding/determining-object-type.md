---
title: Bestimmen des Objekttyps
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 3b1c4ad0ab4fd8d2897aff6ad9097cdc81272455
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410643"
---
# <a name="determining-object-type-visual-basic"></a>Bestimmen des Objekttyps (Visual Basic)
Generische Objektvariablen (d. h. Variablen, die Sie als deklarieren `Object` ) können Objekte aus beliebigen Klassen enthalten. Wenn Sie Variablen vom Typ verwenden `Object` , müssen Sie möglicherweise basierend auf der-Klasse des-Objekts verschiedene Aktionen durchführen, z. b. können einige Objekte eine bestimmte Eigenschaft oder Methode nicht unterstützen. Visual Basic bietet zwei Möglichkeiten, um zu bestimmen, welcher Objekttyp in einer Objektvariablen gespeichert wird: die `TypeName` -Funktion und der- `TypeOf...Is` Operator.  
  
## <a name="typename-and-typeofis"></a>Typname und typeof... Richtet  
 Die `TypeName` -Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, wenn Sie den Klassennamen eines Objekts speichern oder anzeigen müssen, wie im folgenden Code Fragment gezeigt:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 Der `TypeOf...Is` -Operator ist die beste Wahl, um den Typ eines Objekts zu testen, da er viel schneller ist als ein entsprechender Zeichen folgen Vergleich mit `TypeName` . Das folgende Code Fragment verwendet `TypeOf...Is` in einer- `If...Then...Else` Anweisung:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Hier ist ein Wort mit Bedacht. Der- `TypeOf...Is` Operator gibt zurück `True` , wenn ein Objekt einen bestimmten Typ hat oder von einem bestimmten Typ abgeleitet ist. Fast alles, was Sie mit Visual Basic tun, umfasst-Objekte, die einige Elemente enthalten, die normalerweise nicht als Objekte angesehen werden, z. b. Zeichen folgen und ganze Zahlen Diese Objekte werden von abgeleitet und Erben Methoden von <xref:System.Object> . Wenn ein `Integer` und mit ausgewertet `Object` wird, `TypeOf...Is` gibt der Operator zurück `True` . Im folgenden Beispiel wird berichtet, dass der `InParam` -Parameter sowohl ein `Object` als auch ein ist `Integer` :  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 Im folgenden Beispiel wird sowohl `TypeOf...Is` als auch verwendet `TypeName` , um den Objekttyp zu bestimmen, der im-Argument an ihn übermittelt wird `Ctrl` Die `TestObject` Prozedur ruft `ShowType` mit drei unterschiedlichen Arten von Steuerelementen auf.  
  
#### <a name="to-run-the-example"></a>So führen Sie das Beispiel aus  
  
1. Erstellen Sie ein neues Windows-Anwendungsprojekt, und fügen Sie <xref:System.Windows.Forms.Button> dem Formular ein Steuerelement, ein <xref:System.Windows.Forms.CheckBox> -Steuerelement und ein-Steuerelement hinzu <xref:System.Windows.Forms.RadioButton> .  
  
2. Klicken Sie in der Schaltfläche auf dem Formular auf die `TestObject` Prozedur.  
  
3. Fügen Sie dem Formular folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen](calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [If...Then...Else-Anweisung](../../../language-reference/statements/if-then-else-statement.md)
- [String-Datentyp](../../../language-reference/data-types/string-data-type.md)
- [Integer-Datentyp](../../../language-reference/data-types/integer-data-type.md)
