---
title: "Determining Object Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "classes [Visual Basic], discovering which an object belongs to"
  - "types [Visual Basic], determining Visual Basic object types"
  - "object variables, testing values"
  - "TypeOf...Is expression, object type at run time"
  - "TypeName function"
  - "objects [Visual Basic], type determining"
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Determining Object Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Generische Objektvariablen, d. h. als `Object` deklarierte Variablen, können Objekte aus allen Klassen enthalten.  Wenn Sie Variablen vom Typ `Object` verwenden, müssen Sie möglicherweise andere Aktionen auf Grundlage der Klasse des Objekts ausführen; einige Objekte bieten z. B. möglicherweise keine Unterstützung für bestimmte Eigenschaften oder Methoden.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] bietet zwei Möglichkeiten, den in einer Objektvariablen gespeicherten Typ zu bestimmen: die `TypeName`\-Funktion und den `TypeOf...Is`\-Operator.  
  
## TypeName und TypeOf…Is  
 Die `TypeName`\-Funktion gibt eine Zeichenfolge zurück, deren Verwendung sich beim Speichern oder Anzeigen des Klassennamens eines Objekts, wie im folgenden Codefragment gezeigt, empfiehlt:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#92)]  
  
 Der Operator `TypeOf...Is` ist beim Testen des Objekttyps empfehlenswert, da er viel schneller als ein entsprechender Zeichenfolgenvergleich mit `TypeName` ist.  Im folgenden Codefragment wird `TypeOf...Is` in einer `If...Then...Else`\-Anweisung verwendet:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#93)]  
  
 Dabei müssen Sie allerdings folgende Besonderheiten beachten.  Der Operator `TypeOf...Is` gibt `True` zurück, wenn ein Objekt eines bestimmten Typs vorliegt oder von einem bestimmten Typ abgeleitet wurde.  Beinahe jeder Vorgang in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] umfasst Objekte, wozu auch solche Elemente gehören, die normalerweise nicht als Objekte betrachtet werden, z. B. String\- und Integer\-Werte.  Diese Objekte sind von <xref:System.Object> abgeleitet und erben Methoden von dieser Klasse.  Wenn dem Operator `TypeOf...Is` ein `Integer`\-Wert übergeben und nach `Object` überprüft wird, ergibt die Auswertung `True`.  Im folgenden Beispiel wird gemeldet, dass der Parameter `InParam` gleichzeitig vom Typ `Object` und `Integer` ist:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#94)]  
  
 Im folgenden Beispiel werden sowohl `TypeOf...Is` als auch `TypeName` benutzt, um den Typ des im `Ctrl`\-Argument übergebenen Objekts zu ermitteln.  Die `TestObject`\-Prozedur ruft `ShowType` mit drei verschiedenen Steuerelementen auf.  
  
#### So führen Sie das Beispiel aus  
  
1.  Erstellen Sie ein neues Windows\-Anwendungsprojekt, und fügen Sie dem Formular ein <xref:System.Windows.Forms.Button>\-Steuerelement, ein <xref:System.Windows.Forms.CheckBox>\-Steuerelement und ein <xref:System.Windows.Forms.RadioButton>\-Steuerelement hinzu.  
  
2.  Rufen Sie die `TestObject`\-Prozedur über die Schaltfläche im Formular auf.  
  
3.  Fügen Sie dem Formular den folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#95)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)