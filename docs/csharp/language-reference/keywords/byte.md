---
title: "byte (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "byte"
  - "byte_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "byte-Schlüsselwort [C#]"
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# byte (C#-Referenz)
Das `byte`\-Schlüsselwort kennzeichnet einen ganzzahligen Typ, in dem Werte wie in der folgenden Tabelle angegeben gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`byte`|0 bis 255|Ganze 8\-Bit\-Zahl ohne Vorzeichen|<xref:System.Byte?displayProperty=fullName>|  
  
## Literale  
 Eine `byte`\-Variable kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
byte myByte = 255;  
```  
  
 In der vorangehenden Deklaration wird das Ganzzahlliteral `255` implizit von [int](../../../csharp/language-reference/keywords/int.md) in `byte` konvertiert.  Wenn der Bereich von `byte` vom Ganzzahlliteral überschritten wird, tritt ein Kompilierungsfehler auf.  
  
## Konvertierungen  
 Es findet eine vordefinierte implizite Konvertierung von `byte` in [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md) statt.  
  
 Numerische Typen mit einer größeren Speichergröße, die keine Literale sind, können nicht implizit in `byte` konvertiert werden.  Weitere Informationen zu Speichergrößen von ganzzahligen Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md).  Betrachten Sie z. B. die beiden folgenden `byte`\-Variablen `x` und `y`:  
  
```  
  
byte x = 10, y = 20;  
```  
  
 Die folgende Zuweisungsanweisung führt zu einem Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig den Wert `int` annimmt.  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Verwenden Sie zur Problembehebung eine Typumwandlung:  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 Es können jedoch die folgenden Anweisungen verwendet werden, bei denen die Zielvariable dieselbe oder eine höhere Speichergröße aufweist:  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Darüber hinaus werden Gleitkommatypen nicht implizit in `byte` konvertiert.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 Beim Aufrufen überladener Methoden muss eine Typumwandlung erfolgen.  Betrachten Sie z. B. die folgenden überladenen Methoden, die die Parameter `byte` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 Die Verwendung der `byte`\-Typumwandlung gewährleistet, dass der richtige Typ aufgerufen wird. Beispiel:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 Weitere Informationen über arithmetische Ausdrücke aus Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Byte>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)