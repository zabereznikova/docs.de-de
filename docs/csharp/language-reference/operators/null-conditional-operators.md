---
title: NULL-bedingte Operatoren (C# und Visual Basic)
ms.date: 04/03/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: f00d5e489931d9c1172a21ee5f0d3e3d0a6f4a4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408997"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. und ?[]: NULL-bedingte Operatoren (C# und Visual Basic)
Diese Operatoren testen, ob der Wert des linken Operanden NULL ist, bevor ein Memberzugriffs- (`?.`) oder Indexzugriffsvorgang (`?[]`) ausgeführt wird. Sie geben `null` zurück, wenn der linke Operand `null` ergibt. 

Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.  
  
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
  
 Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.  Wenn ein Vorgang in einer Kette von bedingten Memberzugriffs- und Indexvorgängen null zurückgibt, wird die restliche Ausführung der Kette angehalten.  Im folgenden Beispiel wird `E` nicht ausgeführt, wenn das Ergebnis der Auswertung von `A`, `B` oder `C` NULL ist.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 Ein weiterer Verwendungszweck für den NULL-bedingten Memberzugriff ist das Aufrufen von Delegaten auf threadsichere Weise mit viel weniger Code.  Die bisherige Methode erfordert Code wie den folgenden:  
  
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
PropertyChanged?.Invoke(…)  
```  

```vb
PropertyChanged?.Invoke(…)
```  
  
 Die neue Methode ist threadsicher, da der Compiler Code zum Auswerten von `PropertyChanged` nur einmal generiert und das Ergebnis in einer temporären Variablen behält. Sie müssen die `Invoke`-Methode explizit aufrufen, da es keine Aufrufsyntax für Null-Bedingungsdelegate gibt `PropertyChanged?(e)`.  
  
## <a name="language-specifications"></a>Sprachspezifikationen  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Weitere Informationen finden Sie in der [Sprachreferenz für Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [?? (NULL-Sammeloperator)](null-coalescing-operator.md)  
- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)
