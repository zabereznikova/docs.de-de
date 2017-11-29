---
title: Bestimmen des Objekttyps (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9a63b5cf5941deb4dcc7518880b4dc7d0545803c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="determining-object-type-visual-basic"></a>Bestimmen des Objekttyps (Visual Basic)
Generische Objektvariablen (d. h. Variablen Sie als deklarieren `Object`) Objekte aus einer Klasse enthalten kann. Bei Verwendung von Variablen des Typs `Object`, müssen Sie möglicherweise unterschiedliche Aktionen basierend auf der Klasse des Objekts, z. B. einige Objekte möglicherweise nicht unterstützen, eine bestimmte Eigenschaft oder Methode. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]bietet zwei Möglichkeit zum bestimmen, welche Art von Objekt in der Objektvariable gespeichert ist: der `TypeName` Funktion und die `TypeOf...Is` Operator.  
  
## <a name="typename-and-typeofis"></a>TypeName "und" TypeOf... Ist  
 Die `TypeName` Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, wenn Sie speichern oder den Klassennamen eines Objekts anzeigen müssen, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 Die `TypeOf...Is` Operator ist die beste Wahl für das Testen des Objekttyps, da er viel schneller als ein entsprechender Zeichenfolgenvergleich mit `TypeName`. Das folgende Codefragment verwendet `TypeOf...Is` innerhalb einer `If...Then...Else` Anweisung:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Vorsicht ist hier fällig. Die `TypeOf...Is` Operator gibt `True` ein Objekt verfügt über einen bestimmten Typ oder einen bestimmten Typ abgeleitet wird. Fast alle Aufgaben, die Sie mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] umfasst Objekte, darunter einige Elemente, die normalerweise nicht als Objekte, z. B. Zeichenfolgen und ganzen Zahlen betrachtet. Diese Objekte abgeleitet sind, erben Sie Methoden aus <xref:System.Object>. Beim Übergeben einer `Integer` und ausgewerteten mit `Object`, `TypeOf...Is` Operator gibt `True`. Im folgenden Beispiel gemeldet, die den Parameter `InParam` ist sowohl ein `Object` und ein `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 Im folgenden Beispiel wird sowohl `TypeOf...Is` und `TypeName` zum Bestimmen des Typs des Objekts übergeben wird, in der `Ctrl` Argument. Die `TestObject` Prozeduraufrufe `ShowType` mit drei verschiedene Arten von Steuerelementen.  
  
#### <a name="to-run-the-example"></a>So führen Sie das Beispiel aus  
  
1.  Erstellen Sie ein neues Windows-Anwendungsprojekt und Hinzufügen einer <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.CheckBox> -Steuerelement, und ein <xref:System.Windows.Forms.RadioButton> Steuerelement dem Formular.  
  
2.  Rufen Sie auf die Schaltfläche auf dem Formular und die `TestObject` Prozedur.  
  
3.  Fügen Sie dem Formular den folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [If...Then...Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
