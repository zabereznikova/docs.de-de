---
title: Bestimmen des Objekttyps (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2486d989801fc4866a50747aa963b509a627994d
ms.lasthandoff: 03/13/2017

---
# <a name="determining-object-type-visual-basic"></a>Bestimmen des Objekttyps (Visual Basic)
Generische Objektvariablen (d. h. deklarierte Variablen als `Object`) können Objekte aus allen Klassen enthalten. Bei Verwendung von Variablen des Typs `Object`, müssen Sie möglicherweise unterschiedliche Aktionen basierend auf der Klasse des Objekts, z. B. einige Objekte möglicherweise nicht unterstützen, eine bestimmte Eigenschaft oder Methode. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]stellt zwei Methoden zum bestimmen, welche Art von Objekt in einer Objektvariablen gespeichert ist: die `TypeName` Funktion und die `TypeOf...Is` Operator.  
  
## <a name="typename-and-typeofis"></a>TypeName und TypeOf... Ist  
 Die `TypeName` -Funktion gibt eine Zeichenfolge zurück und ist die beste Wahl, beim Speichern oder Anzeigen des Klassennamens eines Objekts, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrOOP&#92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 Die `TypeOf...Is` Operator ist die beste Wahl für den Typ eines Objekts, testen, da er viel schneller als ein entsprechender Zeichenfolgenvergleich mit ist `TypeName`. Das folgende Codefragment verwendet `TypeOf...Is` innerhalb einer `If...Then...Else` Anweisung:  
  
 [!code-vb[VbVbalrOOP&#93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Hier ist ein Wort der Warnung fällig. Die `TypeOf...Is` Operator gibt `True` wird ein Objekt eines bestimmten Typs ist, oder von einem bestimmten Typ abgeleitet ist. Fast alle Aufgaben, die Sie mit [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] umfasst Objekte, die einige Elemente, die normalerweise nicht als Objekte betrachtet werden, z. B. Zeichenfolgen und ganze Zahlen enthalten. Diese Objekte werden von abgeleitet und erben Methoden <xref:System.Object>.</xref:System.Object> Beim Übergeben einer `Integer` und ausgewerteten mit `Object`, `TypeOf...Is` Operator gibt `True`. Im folgende Beispiel meldet, der Parameter `InParam` sowohl ein `Object` und ein `Integer`:  
  
 [!code-vb[VbVbalrOOP&#94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 Im folgenden Beispiel wird sowohl `TypeOf...Is` und `TypeName` den Typ des übergebenen Objekts bestimmt die `Ctrl` Argument. Die `TestObject` Prozeduraufrufe `ShowType` mit drei verschiedenen Arten von Steuerelementen.  
  
#### <a name="to-run-the-example"></a>So führen Sie das Beispiel aus  
  
1.  Erstellen Sie ein neues Windows-Anwendungsprojekt und fügen ein <xref:System.Windows.Forms.Button>-Steuerelement, ein <xref:System.Windows.Forms.CheckBox>-Steuerelement und ein <xref:System.Windows.Forms.RadioButton>-Steuerelement auf das Formular.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button>  
  
2.  Rufen Sie über die Schaltfläche im Formular der `TestObject` Verfahren.  
  
3.  Fügen Sie dem Formular den folgenden Code hinzu:  
  
     [!code-vb[VbVbalrOOP&#95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [If... Dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
