---
title: NULL-bedingte Operatoren (C# und Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 6118956a5681ddbeb110f6e01f090b85cdd65089
ms.openlocfilehash: 465a395a33c027132b7890e02d540438096e2073
ms.contentlocale: de-de
ms.lasthandoff: 08/23/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a>NULL-bedingte Operatoren (C# und Visual Basic)
Wird für eine Prüfung auf null verwendet, bevor Sie eine Operation für den Memberzugriff (`?.`) oder die Indizierung (`?[`) ausführen.  Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 Im letzten Beispiel wird veranschaulicht, dass die Null-Bedingungsoperatoren Kurzschlussoperatoren sind.  Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs- und Indexvorgängen null zurückgibt, wird die restliche Ausführung der Kette angehalten.  Andere Vorgänge mit niedrigerer Rangfolge im Ausdruck werden fortgesetzt.  Beispielsweise wird im folgenden Codebeispiel `E` in der zweiten Zeile ausgeführt, und die Operatoren `??` und `==` werden ausgeführt.  In der ersten Zeile ruft `??` einen Kurzschluss hervor, und `E` wird nicht ausgeführt, wenn die linke Seite ungleich NULL ist.
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 Ein weiterer Verwendungszweck für den Null-Bedingungsmemberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.  Die bisherige Methode erfordert Code wie den folgenden:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 Die neue Methode ist viel einfacher:  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält.  
  
 Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.  Es gab zu viele mehrdeutige Analysesituationen.  
  
## <a name="language-specifications"></a>Sprachspezifikationen  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Weitere Informationen finden Sie in der [Sprachreferenz für Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [?? (Nullzusammensetzungsoperator)](null-conditional-operator.md)   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)

