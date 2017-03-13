---
title: "for (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "for"
  - "for_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "for-Schlüsselwort [C#]"
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 39
---
# for (C#-Referenz)
Wenn Sie eine `for` Schleife verwenden, können Sie eine Anweisung oder einen Anweisungsblock wiederholt ausführen, bis ein angegebener Ausdruck zu `false` ergibt.  Diese Art der Schleife ist für das Durchlaufen Arrays und für andere Anwendungen nützlich, in denen Sie vorhersagen, wieoft Sie die Schleife durchlaufen möchten.  
  
## Beispiel  
 Im folgenden Beispiel wird der Wert von `i` in die Konsole geschrieben und erhöht durch 1 während jeder Iteration der Schleife.  
  
 [!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 Die `for`\-Anweisung im vorherigen Beispiel führt die folgenden Aktionen aus.  
  
1.  Zuerst wird der Anfangswert von variablem `i` festgelegt.  Dieser Schritt wird nur einmal, unabhängig davon, wieoft die Schleife wiederholt.  Sie können diese Initialisierung als Geschehen außerhalb des \- Prozesses vorstellen.  
  
2.  Um die Bedingung \(`i <= 5`\) auswertet, wird der Wert von 5 bis `i` . verglichen.  
  
    -   Wenn `i` kleiner oder gleich 5 ist, ist die Bedingung zu `true` aus, und die folgenden Aktionen wird ausgeführt.  
  
        1.  Die `Console.WriteLine`\-Anweisung im Text der Schleife wird der Wert von `i` an.  
  
        2.  Der Wert von wird von 1. `i` erhöht.  
  
        3.  Die Schleife wird am Anfang des Schritts 2, die Bedingung erneut auszuwerten zurück.  
  
    -   Wenn `i` größer als 5 ist, ist die Bedingung zu `false` aus, und beenden Sie die Schleife.  
  
 Beachten Sie, dass, wenn der Anfangswert von `i` größer als 5 ist, der Text der Schleife nicht noch einmal ausgeführt wird.  
  
 Jede \- Anweisung definiert `for` Initialisierer, Bedingung und Iteratorabschnitte.  Diese Abschnitte normalerweise bestimmen, wieoft die Schleife durchläuft.  
  
```c#  
for (initializer; condition; iterator)  
    body  
```  
  
 Die Abschnitte dienen den folgenden Zwecken.  
  
-   Der Initialisiererabschnitt legt die ursprünglichen Bedingungen fest.  Die Anweisungen in diesem Abschnitt Ausführung nur einmal, bevor Sie die Schleife eingeben.  Der Abschnitt kann nur eine der beiden folgenden Optionen enthalten.  
  
    -   Die Deklaration und die Initialisierung einer Teilnehmeranschlussvariable, als der ersten Beispiel wird gezeigt `int i = 1`\(\).  Auf die Variable ist der \- Schleife lokal und kann nicht außerhalb der Schleife zugegriffen werden.  
  
    -   Beliebige Anweisung expressons in der folgenden Liste, durch Trennzeichen getrennt.  
  
        -   [Zuweisung](../../../csharp/language-reference/operators/assignment-operator.md)\-Anweisung  
  
        -   Aufruf einer Methode  
  
        -   Präfix oder Postfix [Inkrement](../../../csharp/language-reference/operators/increment-operator.md) Ausdruck, z `++i` oder `i++`  
  
        -   Präfix oder Postfix [Dekrement](../../../csharp/language-reference/operators/decrement-operator.md) Ausdruck, z `--i` oder `i--`  
  
        -   Erstellen eines Objekts mithilfe von [neu](../../../csharp/language-reference/keywords/new-operator.md)  
  
        -   [Sie erwarten](../../../csharp/language-reference/keywords/await.md) Ausdruck  
  
-   Der Bedingungsabschnitt enthält einen booleschen Ausdruck, der ausgewertet wird, um zu bestimmen, ob die Schleife beendet werden soll oder erneut ausgeführt werden soll.  
  
-   Der Iteratorabschnitt definiert, was nach jeder Iteration im Text der Schleife geschieht.  Der Iteratorabschnitt enthält null oder mehrere der folgenden Anweisungsausdrücke, durch Trennzeichen getrennt:  
  
    -   [Zuweisung](../../../csharp/language-reference/operators/assignment-operator.md)\-Anweisung  
  
    -   Aufruf einer Methode  
  
    -   Präfix oder Postfix [Inkrement](../../../csharp/language-reference/operators/increment-operator.md) Ausdruck, z `++i` oder `i++`  
  
    -   Präfix oder Postfix [Dekrement](../../../csharp/language-reference/operators/decrement-operator.md) Ausdruck, z `--i` oder `i--`  
  
    -   Erstellen eines Objekts mithilfe von [neu](../../../csharp/language-reference/keywords/new-operator.md)  
  
    -   [Sie erwarten](../../../csharp/language-reference/keywords/await.md) Ausdruck  
  
-   Der Text der Schleife besteht aus einer Anweisung, eine leere Anweisung oder ein Block von Anweisungen, die Sie erstellen, indem Sie dem null oder mehr Anweisungen in geschweiften Klammern.  
  
     Sie können aus einer `for` Schleife ausbrechen, indem Sie das \- Schlüsselwort [Unterbrechung](../../../csharp/language-reference/keywords/break.md) verwenden, oder Sie können zur nächsten Iteration schrittweise durchlaufen, indem Sie das \- Schlüsselwort [Fortfahren](../../../csharp/language-reference/keywords/continue.md) verwenden.  Sie können jede \- Schleife auch beenden, indem Sie [goto](../../../csharp/language-reference/keywords/goto.md), eine [Rückgabe](../../../csharp/language-reference/keywords/return.md) oder [Throw](../../../csharp/language-reference/keywords/throw.md)\-Anweisung verwenden.  
  
 Im ersten Beispiel in diesem Thema werden die gängigste Art von `for` Schleife an, die die folgenden Optionen für die Abschnitte gilt.  
  
-   Der Initialisierer deklariert und initialisiert eine Teilnehmeranschlussvariable, `i`, die eine Anzahl der Iterationen der Schleife beibehält.  
  
-   Die Zustandsüberprüfungen der Wert der Schleifenvariable für einen bekannten endgültigen Wert, 5.  
  
-   Der Iteratorabschnitt verwendet eine Postfixinkrementsanweisung, `i++`, um jede Iteration der Schleife auf Book.  
  
 Im folgenden Beispiel werden einige allgemeine weniger Möglichkeiten: einen Wert zu einer externen Schleifenvariable im Initialisiererabschnitt zuweisen, die `Console.WriteLine`\-Methode im Initialisierer und in den Iteratorabschnitten und das Ändern der Werte von zwei Variablen im Iteratorabschnitt aufgerufen.  
  
 [!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 Alle Ausdrücke, die eine `for`\-Anweisung definieren, sind optional.  Beispielsweise erstellt die folgende Anweisung eine Endlosschleife.  
  
 [!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [for\-Anweisung \(C\+\+\)](/visual-cpp/cpp/for-statement-cpp)   
 [Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)