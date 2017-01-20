---
title: "Anweisungen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Anweisungen"
  - "Anweisungen [C#], Informationen über Anweisungen"
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Anweisungen (C#-Programmierhandbuch)
Die Aktionen, die ein Programm ausführt, werden in Anweisungen ausgedrückt.  Zu den üblichen Aktionen gehören das Deklarieren von Variablen, das Zuweisen von Werten, das Aufrufen von Methoden, das Durchlaufen von Auflistungen und die Verzweigung in unterschiedliche Codeblöcke in Abhängigkeit von einer gegebenen Bedingung.  Die Reihenfolge, in der Anweisungen in einem Programm ausgeführt werden, wird als Ablaufsteuerung oder Ausführungsablauf bezeichnet.  Die Ablaufsteuerung kann bei jeder Programmausführung unterschiedlich sein. Sie ist von den Reaktionen des Programms auf Eingaben zur Laufzeit abhängig.  
  
 Eine Anweisung kann aus einer einzigen Codezeile mit Semikolon am Ende oder einer Folge von einzeiligen Anweisungen in einem Block bestehen.  Ein Anweisungsblock ist in geschweifte Klammern \({}\) eingeschlossen und kann geschachtelte Blöcke enthalten.  Im folgenden Code werden zwei Beispiele für einzeilige Anweisungen und ein mehrzeiliger Anweisungsblock dargestellt:  
  
 [!code-cs[csProgGuideStatements#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_1.cs)]  
  
## Typen von Anweisungen  
 In der folgenden Tabelle sind die verschiedenen Typen von Anweisungen in C\# und deren zugehörige Schlüsselwörter sowie Links zu Themen aufgeführt, die weitere Informationen enthalten:  
  
|Kategorie|C\#\-Schlüsselwörter\/Hinweise|  
|---------------|------------------------------------|  
|Deklarationsanweisungen|Mit einer Deklarationsanweisung wird eine neue Variable oder Konstante eingeführt.  In einer Variablendeklaration kann der Variable optional ein Wert zugewiesen werden.  In der Deklaration einer Konstanten ist die Zuweisung erforderlich.<br /><br /> [!code-cs[csProgGuideStatements#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_2.cs)]|  
|Ausdrucksanweisungen|Ausdrucksanweisungen, mit denen ein Wert berechnet wird, müssen den Wert in einer Variablen speichern.<br /><br /> [!code-cs[csProgGuideStatements#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_3.cs)]|  
|[Auswahlanweisungen](../../../csharp/language-reference/keywords/selection-statements.md)|Mithilfe von Auswahlanweisungen kann in Abhängigkeit von einer oder mehreren angegebenen Bedingungen in verschiedene Abschnitte im Code verzweigt werden.  Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> ["if"](../../../csharp/language-reference/keywords/if-else.md), ["else"](../../../csharp/language-reference/keywords/if-else.md), ["switch"](../../../csharp/language-reference/keywords/switch.md), ["case"](../../../csharp/language-reference/keywords/switch.md)|  
|[Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)|Mit Iterationsanweisungen können Auflistungen wie Arrays durchlaufen oder dieselben Sätze von Anweisungen wiederholt ausgeführt werden, bis eine angegebene Bedingung erfüllt ist.  Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> ["do"](../../../csharp/language-reference/keywords/do.md), ["for"](../../../csharp/language-reference/keywords/for.md), ["foreach"](../../../csharp/language-reference/keywords/foreach-in.md), ["in"](../../../csharp/language-reference/keywords/foreach-in.md), ["while"](../../../csharp/language-reference/keywords/while.md)|  
|[Sprunganweisungen](../../../csharp/language-reference/keywords/jump-statements.md)|Sprunganweisungen übergeben die Steuerung an einen anderen Abschnitt im Code.  Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md)|Ausnahmebehandlungsanweisungen ermöglichen die normale Wiederherstellung bei zur Laufzeit auftretenden Ausnahmebedingungen.  Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> ["throw"](../../../csharp/language-reference/keywords/throw.md), ["try\-catch"](../../../csharp/language-reference/keywords/try-catch.md), ["try\-finally"](../../../csharp/language-reference/keywords/try-finally.md), ["try\-catch\-finally"](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[checked und unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Mit der **checked**\-Anweisung und der **unchecked**\-Anweisung kann angegeben werden, ob numerische Operationen einen Überlauf verursachen dürfen, wenn das Ergebnis in einer Variablen gespeichert wird, deren Wertebereich zu klein für den Ergebniswert ist.  Weitere Informationen finden Sie unter [checked](../../../csharp/language-reference/keywords/checked.md) und [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Die `await`\-Anweisung|Wenn Sie eine Methode mit dem [async](../../../csharp/language-reference/keywords/async.md)\-Modifizierer markieren, können Sie den [Sie erwarten](../../../csharp/language-reference/keywords/await.md)\-Operator in der \- Methode verwenden.  Wenn `await`\-Steuerelement einen Ausdruck in der asynchrone Methode erreicht, kehrt die Steuerung an den Aufrufer zurück, und Status in der \- Methode wird angehalten, bis die erwartete Aufgabe ausführt.  Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Methode fortsetzen.<br /><br /> Ein einfaches Beispiel finden Sie im Abschnitt "Async\-Methoden" von [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).  Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).|  
|Die `yield return`\-Anweisung|Ein Iterator führt eine benutzerdefinierte Iteration über eine Auflistung, wie einer Liste oder einem Array aus.  Ein [Rendite](../../../csharp/language-reference/keywords/yield.md) Iterator verwendet die \- Anweisung, um jedes Element einzeln zurückzugeben.  Wenn eine `yield return`\-Anweisung erreicht ist, wird an die aktuelle Position im Code gespeichert.  Die Ausführung von diesem Speicherort neu gestartet, wenn der Iterator beim nächsten Mal aufgerufen werden.<br /><br /> Weitere Informationen finden Sie unter [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).|  
|Die `fixed`\-Anweisung|Mit der **fixed**\-Anweisung wird verhindert, dass der Garbage Collector eine bewegliche Variable verschiebt.  Weitere Informationen finden Sie unter [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Die `lock`\-Anweisung|Mit der **lock**\-Anweisung kann der Zugriff auf Codeblöcke auf jeweils einen Thread eingeschränkt werden.  Weitere Informationen finden Sie unter [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Anweisungen mit Bezeichnung|Sie können eine Anweisung mit einer Bezeichnung versehen und mit dem [goto](../../../csharp/language-reference/keywords/goto.md)\-Schlüsselwort zu dieser Anweisung mit Bezeichnung springen.  \(Siehe das Beispiel in der folgenden Zeile.\)|  
|Die leere Anweisung|Die leere Anweisung besteht aus einem einzelnen Semikolon.  Sie führt keine Aktionen aus und kann an Stellen verwendet werden, an denen eine Anweisung erforderlich ist, jedoch keine Aktion ausgeführt werden soll.  In den folgenden Beispielen werden zwei Verwendungen einer leeren Anweisung veranschaulicht:<br /><br /> [!code-cs[csProgGuideStatements#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_4.cs)]|  
  
## Eingebettete Anweisungen  
 Auf einige Anweisungen, einschließlich [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) und [foreach](../../../csharp/language-reference/keywords/foreach-in.md), folgt stets eine eingebettete Anweisung.  Diese eingebettete Anweisung kann entweder aus einer einzelnen Anweisung oder aus mehreren, mit geschweiften Klammern \({}\) in einen Anweisungsblock eingeschlossene Anweisungen bestehen.  Wie im folgenden Beispiel gezeigt, können auch einzeilige eingebettete Anweisungen in geschweifte Klammern \({}\) eingeschlossen werden:  
  
 [!code-cs[csProgGuideStatements#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_5.cs)]  
  
 Bei einer nicht in geschweifte Klammern eingeschlossenen eingebetteten Anweisung darf es sich nicht um eine Deklarationsanweisung oder eine Anweisung mit Bezeichnung handeln.  Dies wird im folgenden Beispiel dargestellt:  
  
 [!code-cs[csProgGuideStatements#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_6.cs)]  
  
 Fügen Sie die eingebettete Anweisung in einen Block ein, um den Fehler zu beheben:  
  
 [!code-cs[csProgGuideStatements#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_7.cs)]  
  
## Geschachtelte Anweisungsblöcke  
 Wie im folgenden Code dargestellt, können Anweisungsblöcke geschachtelt werden:  
  
 [!code-cs[csProgGuideStatements#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_8.cs)]  
  
## Nicht erreichbare Anweisungen  
 Wenn der Compiler feststellt, dass die Ablaufsteuerung eine bestimmte Anweisung unter keinen Umständen erreichen kann, löst er die Warnung "CS0162" aus. Dies wird im folgenden Beispiel dargestellt:  
  
 [!code-cs[csProgGuideStatements#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_9.cs)]  
  
## Verwandte Abschnitte  
  
-   [Anweisungsschlüsselwörter](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)