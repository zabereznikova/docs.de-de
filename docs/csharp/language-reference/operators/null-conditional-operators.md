---
title: "NULL-bedingte Operatoren (C# und Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 3
---
# NULL-bedingte Operatoren (C# und Visual Basic)
Wird für eine Prüfung auf null verwendet, bevor Sie eine Operation für den Memberzugriff \(`?.`\) oder die Indizierung \(`?[`\) ausführen.  Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.  
  
```c#  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
```vb  
Dim length = customers?.Length  ‘’ null if customers is null  
Dim first as Customer = customers?(0);  ‘’ null if customers is null  
Dim count as Integer? = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
 Im letzten Beispiel wird veranschaulicht, dass die Null\-Bedingungsoperatoren Kurzschlussoperatoren sind.  Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs\- und Indexvorgängen null zurückgibt, wird die restliche Ausführung der Kette angehalten.  Andere Vorgänge mit niedrigerer Rangfolge im Ausdruck werden fortgesetzt.  Beispielsweise wird `E` im Folgenden immer ausgeführt, und die `??`\- und `==`\-Vorgänge werden ausgeführt.  
  
```vb-c#  
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
  
```  
  
 Ein weiterer Verwendungszweck für den Null\-Bedingungsmemberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.  Die bisherige Methode erfordert Code wie den folgenden:  
  
```c#  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…)  
  
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
  
```  
  
 Die neue Methode ist viel einfacher:  
  
```vb-c#  
PropertyChanged?.Invoke(e)  
  
```  
  
 Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in der temporären Variablen behält.  
  
 Sie müssen die `Invoke`\-Methode explizit aufrufen, da es keine Aufrufsyntax für Null\-Bedingungsdelegate gibt `PropertyChanged?(e)`.  Es gab zu viele mehrdeutige Analysesituationen.  
  
## Sprachspezifikationen  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
 Weitere Informationen finden Sie in der [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)   
 [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)