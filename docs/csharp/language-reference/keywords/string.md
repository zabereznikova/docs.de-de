---
title: "string (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string"
  - "string_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zeichenfolgen [C#], Referenz"
  - "@ Zeichenfolgenliteral"
  - "Zeichenfolgenliterale [C#]"
  - "Zeichenfolgen-Schlüsselwort [C#]"
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# string (C#-Referenz)
Der `string`\-Typ stellt eine Sequenz aus null oder mehr Unicode\-Zeichen dar.  Der `string`\-Typ ist ein Alias für <xref:System.String> in .NET Framework.  
  
 `string` ist zwar ein Verweistyp, aber die Gleichheitsoperatoren \(`==` und `!=`\) sind so definiert, dass sie die Werte von `string`\-Objekten und nicht von Verweisen vergleichen.  Tests für die Übereinstimmung von Zeichenfolgen lassen sich auf diese Weise intuitiver gestalten.  Beispiel:  
  
```c#  
  
      string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 Hiermit wird "True" und dann "False" angezeigt, da der Inhalt der Zeichenfolgen äquivalent ist, aber `a` und `b` nicht auf dieselbe Zeichenfolgeninstanz verweisen.  
  
 Durch den Operator "\+" werden Zeichenfolgen verkettet:  
  
```c#  
  
string a = "good " + "morning";  
```  
  
 Hiermit wird ein Zeichenfolgenobjekt erstellt, das "good morning" enthält.  
  
 Zeichenfolgen sind *unveränderlich*, d. h. der Inhalt eines Zeichenfolgenobjekts kann nicht mehr geändert werden, nachdem das Objekt erstellt wurde, auch wenn die Syntax etwas anderes vermuten lässt.  Wenn Sie z. B. den folgenden Code schreiben, erstellt der Compiler für die neue Zeichenabfolge ein neues Zeichenfolgenobjekt, und das neue Objekt wird "b" zugewiesen.  Die Zeichenfolge "h" ist in diesem Fall für Garbage Collection geeignet.  
  
```c#  
  
      string b = "h";  
b += "ello";  
```  
  
 Mit dem Operator \[\] kann auf einzelne Zeichen eines `string` mit Schreibschutz zugegriffen werden:  
  
```c#  
  
      string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 Zeichenfolgenliterale sind vom `string`\-Typ und können in zwei Formaten geschrieben werden: in Anführungszeichen oder mit vorangestelltem @\-Zeichen.  Bei der ersten Möglichkeit werden Literale in doppelte Anführungszeichen \("\) eingeschlossen:  
  
```c#  
"good morning"  // a string literal  
```  
  
 Zeichenfolgenliterale können jedes Zeichenliteral enthalten.  Escapesequenzen werden eingeschlossen.  Im folgenden Beispiel wird die Escapesequenz `\\` für umgekehrte Schrägstriche verwendet, `\u0066` wird für den Buchstaben f verwendet und `\n` für Zeilenumbrüche.  
  
```  
  
      string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  Der Escapecode `\`u`dddd` stellt das Unicode\-Zeichen U\+`dddd` dar \(wobei `dddd` für eine vierstellige Zahl steht\).  Auch achtstelliger Unicode\-Escapecode wird erkannt: `\Udddddddd`.  
  
 Bei der Schreibweise mit vorangestelltem @\-Zeichen beginnen wörtliche Zeichenfolgenliterale mit @ und sind ebenfalls in doppelte Anführungszeichen eingeschlossen.  Beispiel:  
  
```c#  
@"good morning"  // a string literal  
```  
  
 Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z. B. das Schreiben vollqualifizierter Dateinamen erleichtert wird:  
  
```c#  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 Um ein doppeltes Anführungszeichen in einer Zeichenfolge mit vorangestelltem @\-Zeichen zu verwenden, verdoppeln Sie es:  
  
```c#  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 Ein weiterer Verwendungszweck des @\-Symbols besteht in der Verwendung von referenzierten Bezeichnern \([\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)\), die gleichzeitig C\#\-Schlüsselwörter sind.  
  
 Weitere Informationen über Zeichenfolgen in C\# finden Sie im [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md).  
  
## Beispiel  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../Topic/Best%20Practices%20for%20Using%20Strings%20in%20the%20.NET%20Framework.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)   
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)   
 [Grundlegende Zeichenfolgenoperationen](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)   
 [Erstellen neuer Zeichenfolgen](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Tabelle zur Formatierung numerischer Ergebnisse](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)