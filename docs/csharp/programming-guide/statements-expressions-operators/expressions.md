---
title: "Ausdr&#252;cke (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Ausdrücke"
  - "Ausdrücke [C#]"
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Ausdr&#252;cke (C#-Programmierhandbuch)
Ein *Ausdruck* ist eine Folge von mindestens einem Operanden und optionalen Operatoren, die zu einem einzelnen Wert, einem einzelnen Objekt, einer einzelnen Methode oder einem einzelnen Namespace ausgewertet werden kann.  Ausdrücke können aus einem literalen Wert, einem Methodenaufruf, einem Operator und dessen Operanden oder einem *einfachen Namen* bestehen.  Einfache Namen können der Name einer Variablen bzw. eines Typmembers, Methodenparameters, Namespaces oder Typs sein.  
  
 Ausdrücke können Operatoren verwenden. Diese können wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden, deren Parameter wiederum andere Methodenaufrufe darstellen. Die Bandbreite der möglichen Ausdrücke reicht also von einfach bis sehr komplex.  Im Folgenden sind zwei Beispiele für Ausdrücke aufgeführt:  
  
```  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25))   
System.Convert.ToInt32("35")  
```  
  
## Ausdruckswerte  
 In den meisten Zusammenhängen, in denen Ausdrücke verwendet werden, beispielsweise in Anweisungen oder Methodenparametern, muss der Ausdruck zu einem Wert ausgewertet werden.  Wenn x und y ganze Zahlen sind, ergibt der Ausdruck `x + y` einen numerischen Wert.  Der Ausdruck `new MyClass()` wird zu einem Verweis auf eine neue Instanz eines `MyClass`\-Objekts ausgewertet.  Der Ausdruck `myClass.ToString()` wird zu einer Zeichenfolge ausgewertet, da dies der Rückgabetyp der Methode ist.  Auch wenn ein Namespacename als Ausdruck klassifiziert ist, wird dieser jedoch nicht zu einem Wert ausgewertet und kann daher nicht als Endergebnis eines Ausdrucks auftreten.  Ein Namespacename kann nicht einem Methodenparameter übergeben, in einem neuen Ausdruck verwendet oder einer Variablen zugewiesen werden.  Er kann nur als Unterausdruck in einem größeren Ausdruck verwendet werden.  Das Gleiche gilt für Typen \(im Unterschied zu <xref:System.Type?displayProperty=fullName>\-Objekten\), Methodengruppennamen \(im Unterschied zu spezifischen Methoden\) sowie [add](../../../csharp/language-reference/keywords/add.md)\-Ereignisaccessoren und [remove](../../../csharp/language-reference/keywords/remove.md)\-Ereignisaccessoren.  
  
 Jeder Wert verfügt über einen zugeordneten Typ.  Wenn beispielsweise x und y Variablen vom Typ `int` sind, wird der Wert des Ausdrucks `x + y` ebenfalls als `int` typisiert.  Wenn der Wert einer Variablen eines anderen Typs zugewiesen wird, oder wenn x und y von unterschiedlichen Typen sind, werden die Regeln der Typkonvertierung angewendet.  Weitere Informationen über die Funktionsweise solcher Konvertierungen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
## Überläufe  
 Numerische Ausdrücke können Überläufe zur Folge haben, wenn ihr Wert größer ist als der maximale Wert des Typs des Werts.  Weitere Informationen finden Sie unter [Checked und Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) und [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
## Operatorrangfolge und Assoziativität  
 Die Auswertung eines Ausdrucks wird durch die Regeln der Assoziativität und der Operatorrangfolge bestimmt.  Weitere Informationen finden Sie unter [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md).  
  
 Die meisten Ausdrücke, mit Ausnahme von Zuweisungsausdrücken und Ausdrücken für Methodenaufrufe, müssen in eine Anweisung eingebettet werden.  Weitere Informationen finden Sie unter [Anweisungen](../../../csharp/programming-guide/statements-expressions-operators/statements.md).  
  
## Literale und einfache Namen  
 Die zwei einfachsten Typen von Ausdrücken sind Literale und einfache Namen.  Ein Literal ist ein konstanter Wert, der keinen Namen hat.  Im folgenden Codebeispiel sind sowohl `5` als auch `"Hello World"` literale Werte:  
  
 [!code-cs[csProgGuideStatements#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/expressions_1.cs)]  
  
 Weitere Informationen zu literalen Werten finden Sie unter [Typen](../../../csharp/language-reference/keywords/types.md).  
  
 Im vorhergehenden Beispiel sind sowohl `i` als auch `s` einfache Namen, die lokale Variablen identifizieren.  Wenn diese Variablen in einem Ausdruck verwendet werden, wird der Name der Variablen zum aktuell am Speicherort der Variablen gespeicherten Wert ausgewertet.  Dies wird im folgenden Beispiel dargestellt:  
  
 [!code-cs[csProgGuideStatements#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/expressions_2.cs)]  
  
## Aufrufausdrücke  
 Im folgenden Codebeispiel ist der Aufruf von `DoWork` ein Aufrufausdruck.  
  
```  
DoWork();  
```  
  
 Für einen Methodenaufruf werden der Name der Methode \(entweder als Name wie im vorigen Beispiel oder als Ergebnis eines anderen Ausdrucks\) und eine Klammer mit allen Methodenparametern benötigt.  Weitere Informationen finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).  Ein Delegataufruf verwendet den Namen des Delegaten mit den Methodenparametern in Klammern.  Weitere Informationen finden Sie unter [Delegaten](../../../csharp/programming-guide/delegates/index.md).  Wenn die Methode einen Wert zurückgibt, wertet der Methodenaufruf bzw. der Delegataufruf den Rückgabewert der Methode aus.  Methoden, die void zurückgeben, können in einem Ausdruck nicht anstelle eines Werts verwendet werden.  
  
## Abfrageausdrücke  
 Die gleichen Regeln für Ausdrücke gelten im Allgemeinen für Abfrageausdrücke.  Weitere Informationen finden Sie unter [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## Lambda\-Ausdrücke  
 Lambda\-Ausdrücke stellen "Inlinemethoden" dar, die keinen Namen haben, aber Eingabeparameter und mehrere Anweisungen umfassen können.  Sie werden häufig in LINQ verwendet, um Argumente an Methoden zu übergeben.  Lambda\-Ausdrücke werden, je nach dem Kontext, in dem sie verwendet werden, entweder zu Delegaten oder Ausdrucksbaumstrukturen kompiliert.  Weitere Informationen finden Sie unter [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
## Ausdrucksbaumstrukturen  
 Ausdrucksbaumstrukturen aktivieren Ausdrücke, um als Datenstrukturen dargestellt zu werden.  Sie werden häufig von LINQ\-Anbietern zum Übersetzen von Abfrageausdrücken in für andere Kontexte, z. B. eine SQL\-Datenbank, verständlichen Code verwendet.  Weitere Informationen finden Sie unter [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Hinweise  
 Wenn in einem Ausdruck eine Variable, ein Objekteigenschaftenzugriff oder ein Objektindexerzugriff erkannt wird, wird der Wert dieses Elements als Wert des Ausdrucks verwendet.  In C\# kann ein Ausdruck an jeder Stelle positioniert sein, an der ein Wert oder Objekt erwartet wird, solange der Ausdruck letztlich zu dem erforderlichen Typ ausgewertet wird.  
  
## Enthaltenes Buchkapitel  
 [Variables and Expressions](http://go.microsoft.com/fwlink/?LinkId=221228) in [Beginning Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [Typen](../../../csharp/programming-guide/types/index.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)