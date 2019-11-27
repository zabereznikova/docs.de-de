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
ms.openlocfilehash: a77cc0603a0b61f58a4aa703c4b1e6ef4c26729c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345197"
---
# <a name="determining-object-type-visual-basic"></a>Bestimmen des Objekttyps (Visual Basic)
Generische Objektvariablen (d. h. Variablen, die Sie als `Object`deklarieren) können Objekte aus beliebigen Klassen enthalten. Wenn Sie Variablen vom Typ `Object`verwenden, müssen Sie möglicherweise basierend auf der-Klasse des-Objekts verschiedene Aktionen durchführen. Beispielsweise unterstützen einige Objekte möglicherweise nicht eine bestimmte Eigenschaft oder Methode. Visual Basic bietet zwei Möglichkeiten, um zu bestimmen, welcher Objekttyp in einer Objektvariablen gespeichert wird: die `TypeName`-Funktion und der `TypeOf...Is`-Operator.  
  
## <a name="typename-and-typeofis"></a>Typname und typeof... Richtet  
 Die `TypeName`-Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, wenn Sie den Klassennamen eines Objekts speichern oder anzeigen müssen, wie im folgenden Code Fragment gezeigt:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 Der `TypeOf...Is`-Operator ist die beste Wahl, um den Typ eines Objekts zu testen, da er viel schneller ist als ein entsprechender Zeichen folgen Vergleich mithilfe von `TypeName`. Das folgende Code Fragment verwendet `TypeOf...Is` in einer `If...Then...Else`-Anweisung:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Hier ist ein Wort mit Bedacht. Der `TypeOf...Is`-Operator gibt `True` zurück, wenn ein Objekt einen bestimmten Typ hat oder von einem bestimmten Typ abgeleitet ist. Fast alles, was Sie mit Visual Basic tun, umfasst-Objekte, die einige Elemente enthalten, die normalerweise nicht als Objekte angesehen werden, z. b. Zeichen folgen und ganze Zahlen Diese Objekte werden von abgeleitet und Erben Methoden von <xref:System.Object>. Wenn eine `Integer` übermittelt und mit `Object`ausgewertet wird, gibt der `TypeOf...Is`-Operator `True`zurück. Im folgenden Beispiel wird berichtet, dass der Parameter `InParam` sowohl ein `Object` als auch ein `Integer`ist:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 Im folgenden Beispiel wird sowohl `TypeOf...Is` als auch `TypeName` verwendet, um den Typ des Objekts zu bestimmen, das im `Ctrl`-Argument an das Objekt übermittelt wird Die `TestObject` Prozedur ruft `ShowType` mit drei unterschiedlichen Arten von Steuerelementen auf.  
  
#### <a name="to-run-the-example"></a>So führen Sie das Beispiel aus  
  
1. Erstellen Sie ein neues Windows-Anwendungsprojekt, und fügen Sie dem Formular ein <xref:System.Windows.Forms.Button>-Steuerelement, ein <xref:System.Windows.Forms.CheckBox>-Steuerelement und ein <xref:System.Windows.Forms.RadioButton>-Steuerelement hinzu.  
  
2. Nennen Sie auf der Schaltfläche auf dem Formular das `TestObject` Prozedur.  
  
3. Fügen Sie dem Formular folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [If...Then...Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
