---
title: "uint (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "uint"
  - "uint_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "uint-Schlüsselwort [C#]"
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# uint (C#-Referenz)
Das `uint`\-Schlüsselwort kennzeichnet einen ganzzahligen Typ, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`uint`|0 bis 4.294.967.295|Vorzeichenlose 32\-Bit\-Ganzzahl|<xref:System.UInt32?displayProperty=fullName>|  
  
 **Hinweis** Der `uint`\-Typ ist nicht CLS\-fähig.  Verwenden Sie wenn möglich `int`.  
  
## Literale  
 Eine Variable vom Typ `uint` kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
  
uint myUint = 4294967290;  
```  
  
 Wenn ein Ganzzahlliteral kein Suffix besitzt, entspricht sein Typ dem ersten der folgenden Typen, mit dem sein Wert dargestellt werden kann: [int](../../../csharp/language-reference/keywords/int.md), `uint`, [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md).  In diesem Beispiel ist dies `uint`:  
  
```  
  
uint uInt1 = 123;  
```  
  
 Sie können auch das Suffix u oder U verwenden. Beispiel:  
  
```  
  
uint uInt2 = 123U;  
```  
  
 Bei Verwendung des Suffixes `U` oder `u` wird der Typ des Ganzzahlliterals je nach numerischem Wert des Literals entweder als `uint` oder `ulong` festgelegt.  Beispiele:  
  
```  
Console.WriteLine(44U.GetType());  
Console.WriteLine(323442434344U.GetType());  
```  
  
 Mit diesem Code wird `System.UInt32` und dahinter `System.UInt64` angezeigt – die zugrunde liegenden Typen für `uint` und `ulong` –, da das zweite Literal zu groß ist, um mit dem `uint`\-Typ gespeichert zu werden.  
  
## Konvertierungen  
 Es findet eine vordefinierte implizite Konvertierung von `uint` in [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md) statt.  Beispiele:  
  
```  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 Es findet eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `uint` statt.  Andernfalls ist eine Typumwandlung erforderlich.  Ohne Umwandlung verursacht die folgende Anweisung beispielsweise einen Kompilierungsfehler:  
  
```  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 Beachten Sie auch, dass Gleitkommatypen nicht implizit in `uint` konvertiert werden.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 Weitere Informationen zu arithmetischen Ausdrücken mit Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.UInt32>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)