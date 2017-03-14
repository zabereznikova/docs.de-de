---
title: "long (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "long_CSharpKeyword"
  - "long"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "long-Schlüsselwort [C#]"
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# long (C#-Referenz)
Das `long`\-Schlüsselwort kennzeichnet einen ganzzahligen Typ, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`long`|\-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807|64\-Bit\-Ganzzahl mit Vorzeichen|<xref:System.Int64?displayProperty=fullName>|  
  
## Literale  
 Eine `long`\-Variable kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
  
long long1 = 4294967296;  
```  
  
 Wenn ein Ganzzahlliteral kein Suffix besitzt, entspricht sein Typ dem ersten der folgenden Typen, mit dem sein Wert dargestellt werden kann: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), `long`, [ulong](../../../csharp/language-reference/keywords/ulong.md).  Im vorangehenden Beispiel ist das Literal vom Typ `long`, da es den Bereich von [uint](../../../csharp/language-reference/keywords/uint.md) überschreitet. \(Informationen zu den Speichergrößen ganzzahliger Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md).\)  
  
 Folgendermaßen können Sie auch das Suffix L mit dem `long`\-Typ verwenden:  
  
```  
  
long long2 = 4294967296L;  
```  
  
 Bei Verwendung des Suffixes L wird der Typ des Ganzzahlliterals abhängig von seiner Größe entweder als `long` oder als [ulong](../../../csharp/language-reference/keywords/ulong.md) festgelegt.  In diesem Fall wird `long` verwendet, da dessen Bereich kleiner ist als der von [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 Suffixe werden häufig beim Aufrufen überladener Methoden eingesetzt.  Betrachten Sie z. B. die folgenden überladenen Methoden, die den `long`\-Parameter und den [int](../../../csharp/language-reference/keywords/int.md)\-Parameter verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 Durch das Suffix **L** wird sichergestellt, dass der richtige Typ aufgerufen wird. Beispiel:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 Sie können den Typ `long` zusammen mit anderen numerischen ganzzahligen Typen in demselben Ausdruck verwenden. In diesem Fall wird der Ausdruck als `long` \(bzw. in relationalen oder booleschen Ausdrücken als [bool](../../../csharp/language-reference/keywords/bool.md)\) ausgewertet.  Der folgende Ausdruck wird beispielsweise als `long` ausgewertet:  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  Der Kleinbuchstabe "l" kann ebenfalls als Suffix verwendet werden.  In diesem Fall wird jedoch eine Compilerwarnung generiert, da der Buchstabe "l" leicht mit der Ziffer "1" verwechselt werden kann. Verwenden Sie zur besseren Unterscheidung den Großbuchstaben "L".  
  
 Weitere Informationen über arithmetische Ausdrücke aus Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
## Konvertierungen  
 Es erfolgt eine vordefinierte implizite Konvertierung von `long` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  Andernfalls muss eine Typumwandlung durchgeführt werden.  Ohne explizite Typumwandlung wird durch die folgende Anweisung z. B. ein Kompilierungsfehler generiert:  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Es erfolgt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `long`.  
  
 Beachten Sie auch, dass Gleitkommatypen nicht implizit in `long` konvertiert werden.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
  
        long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Int64>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)