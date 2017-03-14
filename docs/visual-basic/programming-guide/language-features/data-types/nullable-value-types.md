---
title: "Nullable Value Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Nullable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "nullable types [Visual Basic]"
  - "? [Visual Basic]"
  - "types [Visual Basic], nullable"
  - "nullable types"
  - "data types [Visual Basic], nullable"
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Nullable Value Types (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Zuweilen arbeiten Sie mit einem Werttyp, für den unter bestimmten Umständen kein Wert definiert ist.  Zum Beispiel muss für ein Feld in einer Datenbank möglicherweise unterschieden werden, ob ihm ein Wert zugewiesen ist, der eine Bedeutung hat, oder ob ihm kein Wert zugewiesen ist.  Werttypen können auf ihre normalen Werte oder einen NULL\-Wert erweitert werden.  Eine solche Erweiterung wird als *auf NULL festlegbarer Typ* bezeichnet.  
  
 Jeder auf NULL festlegbare Typ wird anhand der generischen <xref:System.Nullable%601>\-Struktur erstellt.  Angenommen, eine Datenbank verfolgt arbeitsbezogene Aktivitäten nach.  Im folgenden Beispiel wird ein auf NULL festlegbarer `Boolean`\-Typ erstellt und eine Variable von diesem Typ deklariert.  Sie können die Deklaration auf drei Arten schreiben:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 Die Variable `ridesBusToWork` kann den Wert `True`, den Wert `False` oder keinen Wert annehmen.  Ihr standardmäßiger Anfangswert ist kein Wert, was in diesem Fall bedeuten kann, dass die Informationen über diese Person noch nicht abgerufen wurden.  `False` hingegen kann bedeuten, dass die Informationen abgerufen wurden und die Person nicht mit dem Bus zur Arbeit kommt.  
  
 Sie können Variablen und Eigenschaft mit auf NULL festlegbaren Typen deklarieren, und Sie können ein Array mit Elementen eines auf NULL festlegbaren Typs deklarieren.  Sie können Prozeduren mit auf NULL festlegbaren Typen als Parameter deklarieren, und Sie können mit der `Function`\-Prozedur einen auf NULL festlegbaren Typ zurückgeben.  
  
 Sie können keinen auf NULL festlegbaren Typ für einen Referenztyp, z. B. ein Array, einen `String` oder eine Klasse, erstellen.  Der zugrunde liegende Typ muss ein Werttyp sein.  Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## Verwenden einer Variablen mit auf NULL festlegbarem Typ  
 Die wichtigsten Member eines auf NULL festlegbaren Typs sind seine <xref:System.Nullable%601.HasValue%2A>\-Eigenschaft und seine <xref:System.Nullable%601.Value%2A>\-Eigenschaft.  Bei einer Variablen mit auf NULL festlegbarem Typ können Sie mit <xref:System.Nullable%601.HasValue%2A> bestimmen, ob die Variable einen definierten Wert enthält.  Wenn <xref:System.Nullable%601.HasValue%2A> `True` ist, können Sie den Wert von <xref:System.Nullable%601.Value%2A> lesen.  Beachten Sie, dass sowohl <xref:System.Nullable%601.HasValue%2A> als auch <xref:System.Nullable%601.Value%2A> `ReadOnly`\-Eigenschaften sind.  
  
### Standardwerte  
 Wenn Sie eine Variable mit auf NULL festlegbarem Typ deklarieren, ist der Standardwert ihrer <xref:System.Nullable%601.HasValue%2A>\-Eigenschaft `False`.  Dies bedeutet, dass die Variable statt des Standardwerts des ihr zugrunde liegenden Werttyps standardmäßig keinen definierten Wert aufweist.  Im folgenden Beispiel verfügt die Variable `numberOfChildren` ursprünglich über keinen definierten Wert, obwohl der Standardwert des `Integer`\-Typs 0 ist.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Ein NULL\-Wert empfiehlt sich, um einen undefinierten oder unbekannten Wert anzugeben.  Wenn `numberOfChildren` als `Integer` deklariert wurde, ist kein Wert vorhanden, um anzugeben, dass die Informationen gegenwärtig nicht verfügbar sind.  
  
### Speichern von Werten  
 Ein Wert wird in einer Variablen oder Eigenschaft eines auf NULL festlegbaren Typs auf die übliche Weise gespeichert.  Im folgenden Beispiel wird der im vorherigen Beispiel deklarierten Variablen `numberOfChildren` ein Wert zugewiesen.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Wenn eine Variable oder Eigenschaft mit auf NULL festlegbarem Typ einen definierten Wert enthält, können Sie veranlassen, dass sie in ihren ursprünglichen Zustand zurückkehrt, in dem kein Wert zugewiesen war.  Hierzu legen Sie die Variable oder Eigenschaft auf `Nothing` fest, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Obwohl Sie einer Variablen eines auf NULL festlegbaren Typs `Nothing` zuweisen können, ist es nicht möglich, diese mittels Gleichheitszeichen auf `Nothing` zu überprüfen.  Der Vergleich mithilfe des Gleichheitszeichens, `someVar = Nothing`, ergibt immer `Nothing`.  Sie können die <xref:System.Nullable%601.HasValue%2A>\-Eigenschaft der Variablen auf `False` überprüfen oder eine Überprüfung mithilfe des Operators `Is` oder `IsNot` vornehmen.  
  
### Abrufen von Werten  
 Um den Wert einer Variablen mit auf NULL festlegbarem Typ abzurufen, überprüfen Sie zunächst ihre <xref:System.Nullable%601.HasValue%2A>\-Eigenschaft, um sicherzustellen, dass sie einen Wert aufweist.  Wenn Sie versuchen, den Wert zu lesen, und <xref:System.Nullable%601.HasValue%2A> ist `False`, wird von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] eine <xref:System.InvalidOperationException>\-Ausnahme ausgelöst.  Im folgenden Beispiel wird die empfohlene Vorgehensweise zum Lesen der Variablen `numberOfChildren` aus den vorhergehenden Beispielen veranschaulicht.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## Vergleichen von auf NULL festlegbaren Typen  
 Wenn `Boolean`\-Variablen, die NULL\-Werte zulassen, in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False` oder `Nothing` sein.  Im Folgenden ist die Wahrheitstabelle für `And` und `Or` aufgeführt.  Da `b1` und `b2` nun über drei mögliche Werte verfügen, sind neun Kombinationen auszuwerten.  
  
|b1|b2|b1 AND b2|b1 OR b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Ist der Wert von booleschen Variablen oder Ausdrücken `Nothing`, ist er weder `true` noch `false`.  Betrachten Sie das folgende Beispiel.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 In diesem Beispiel ergibt `b1 And b2` den Wert `Nothing`.  Daraus ergibt sich, dass die `Else`\-Klausel in jeder `If`\-Anweisung ausgeführt wird und die Ausgabe wie folgt lautet:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` und `OrElse` verwenden eine Kurzschlussauswertung und müssen ihren jeweils zweiten Operanden auswerten, wenn der erste `Nothing` ergibt.  
  
## Weitergabe  
 Wenn mindestens einer der beiden Operanden einer Vergleichs\-, Schiebe\-, Typ\- oder arithmetischen Operation auf NULL festgelegt werden kann, lässt auch das Ergebnis der Operation NULL\-Werte zu.  Wenn beide Operanden andere Werte als `Nothing` haben, wird die Operation für die zugrunde liegenden Werte der Operanden durchgeführt, als ob keiner der beiden ein Typ wäre, der NULL\-Werte zulässt.  Im folgenden Beispiel werden die Variablen `compare1` und `sum1` implizit typisiert.  Wenn Sie mit der Maus darauf zeigen, sehen Sie, dass der Compiler für beide Typen ableitet, die NULL\-Werte zulassen.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Wenn mindestens einer der beiden Operanden den Wert `Nothing` hat, ist das Ergebnis `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## Verwenden von auf NULL festlegbaren Typen mit Daten  
 Eine Datenbank ist eine der wichtigsten Anwendungsmöglichkeiten für auf NULL festlegbare Typen.  Nicht alle Datenbankobjekte unterstützen gegenwärtig auf NULL festlegbare Typen, doch werden sie von den Designer\-generierten Tabellenadaptern unterstützt.  Siehe "TableAdapter\-Unterstützung für Typen mit NULL\-Wert" in [Übersicht über TableAdapters](/visual-studio/data-tools/tableadapter-overview).  
  
## Siehe auch  
 <xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A>   
 [Verwenden von auf NULL festlegbaren Typen](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Übersicht über TableAdapters](/visual-studio/data-tools/tableadapter-overview)   
 [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)