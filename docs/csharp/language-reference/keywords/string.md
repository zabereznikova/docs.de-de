---
title: string (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a616808a8e6ff5e259c503c0143db4b8f73bdef2
ms.lasthandoff: 03/13/2017

---
# <a name="string-c-reference"></a>string (C#-Referenz)
Der Typ `string` stellt eine Sequenz von Null oder mehr Unicode-Zeichen dar. `string` ist ein Alias für <xref:System.String> in .NET Framework.  
  
 Obwohl `string` ein Verweistyp ist, werden die Gleichheitsoperatoren (`==` und `!=`) zum Vergleichen der Werte von `string`-Objekten, nicht von Verweisen, definiert. Dadurch wird das Testen auf Zeichenfolgengleichheit intuitiver. Zum Beispiel:  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 Dies zeigt TRUE und anschließend FALSE an, weil der Inhalt der Zeichenfolgen gleich sind. Jedoch verweisen `a` und `b` nicht auf die gleiche Zeichenfolgeninstanz.  
  
 Der Operator „+“ verkettet Zeichenfolgen:  
  
```csharp  
string a = "good " + "morning";  
```  
  
 Dadurch wird ein Zeichenfolgenobjekt erstellt, das „Guten Morgen“ enthält.  
  
 Zeichenfolgen sind *unveränderlich*. Die Inhalte eines Zeichenfolgenobjekts können nicht geändert werden, nachdem ein Objekt erstellt wurde, obwohl die Syntax den Eindruck erweckt, dass es machbar wäre. Wenn Sie z.B. diesen Code schreiben, erstellt der Compiler tatsächlich ein neues Zeichenfolgenobjekt, um die neue Zeichensequenz zu speichern. Das neue Objekt wird b zugewiesen. Die Zeichenfolge „h“ ist anschließend für die automatische Speicherbereinigung auswählbar.  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 Der []-Operator kann für schreibgeschützten Zugriff auf einzelne Zeichen eines `string` verwendet werden:  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 Zeichenfolgenliterale sind Typ `string` und können in zwei Formaten geschrieben werden: in Anführungszeichen und @-quoted. Zeichenfolgenliterale in Anführungszeichen werden in doppelte Anführungszeichen (") eingeschlossen:  
  
```csharp  
"good morning"  // a string literal  
```  
  
 Zeichenfolgenliterale können jeden Zeichenliteral enthalten. Escapesequenzen sind enthalten. Im folgenden Beispiel wird die Escapesequenz `\\` für den umgekehrten Schrägstrich, `\u0066` für den Buchstaben „f“ und `\n` für den Zeilenumbruch verwendet.  
  
```  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  Der Escapecode `\`u`dddd` (wobei `dddd` eine vierstellige Zahl ist) stellt das Unicode-Zeichen U+`dddd` dar. Escapecodes aus achtstelligen Unicode werden auch erkannt: `\Udddddddd`.  
  
 Wörtliche Zeichenfolgenliterale beginnen mit @ und sind ebenfalls in doppelte Anführungszeichen eingeschlossen. Zum Beispiel:  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z.B. das Schreiben eines vollqualifizierten Dateinamens erleichtert wird:  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 Verdoppeln Sie das doppelte Anführungszeichen, um es in einer @-quoted-Zeichenfolge aufzunehmen:  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 Eine andere Verwendung des @-Symbols besteht darin, verwiesene ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) Bezeichner zu verwenden, die C#-Schlüsselwörter sind.  
  
 Weitere Informationen zu Zeichenfolgen in C# finden Sie unter [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](http://msdn.microsoft.com/library/b9f0bf53-e2de-4116-8ce9-d4f91a1df4f7)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)   
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)   
 [Grundlegende Zeichenfolgenoperationen](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)   
 [Erstellen neuer Zeichenfolgen](http://msdn.microsoft.com/library/06fdf123-2fac-4459-8904-eb48ab908a30)   
 [Tabelle zur Formatierung numerischer Ergebnisse](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)

