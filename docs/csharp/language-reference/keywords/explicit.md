---
title: "explicit (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "explicit_CSharpKeyword"
  - "explicit"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "explicit-Schlüsselwort [C#]"
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# explicit (C#-Referenz)
Das `explicit`\-Schlüsselwort deklariert einen benutzerdefinierten Typkonvertierungsoperator, der mit einer Umwandlung aufgerufen werden muss.  Der folgende Operator konvertiert zum Beispiel von der Klasse Fahrenheit in die Klasse Celsius:  
  
 [!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_1.cs)]  
  
 Dieser Konvertierungsoperator kann wie folgt aufgerufen werden:  
  
 [!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_2.cs)]  
  
 Der Konvertierungsoperator konvertiert von einem Quelltyp in einen Zieltyp.  Der Quelltyp stellt den Konvertierungsoperator bereit.  Anders als bei der impliziten Konvertierung müssen explizite Konvertierungsoperatoren mittels einer Umwandlung aufgerufen werden.  Ein Konvertierungsvorgang, durch den Ausnahmen verursacht oder Informationen verloren gehen können, sollte als `explicit` gekennzeichnet werden.  Dadurch wird verhindert, dass der Compiler den Konvertierungsvorgang ohne Bestätigung aufruft, was u. U. unvorhersehbare Konsequenzen hätte.  
  
 Das Auslassen der Umwandlung verursacht den Kompilierungsfehler CS0266.  
  
 Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Beispiel  
 Im folgenden Beispiel werden eine `Fahrenheit`\-Klasse und eine `Celsius`\-Klasse bereitgestellt, die beide einen expliziten Operator für die Konvertierung in die jeweils andere Klasse bereitstellen.  
  
 [!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_3.cs)]  
  
## Beispiel  
 Im nachstehenden Beispiel wird eine Struktur `Digit` definiert, die eine einzelne Dezimalstelle repräsentiert.  Für Konvertierungen von `byte` nach `Digit` wird ein Operator definiert. Hierbei handelt sich jedoch um eine explizite Konvertierung, da nicht alle Bytes in einen `Digit`\-Wert konvertiert werden können.  
  
 [!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_4.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Implizite](../../../csharp/language-reference/keywords/implicit.md)   
 [Operator](../../../csharp/language-reference/keywords/operator.md)   
 [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [Verkettete benutzerdefinierte explizite Konvertierungen in C\#](http://go.microsoft.com/fwlink/?LinkId=112384)