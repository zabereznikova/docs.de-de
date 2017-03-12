---
title: "sbyte (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "sbyte_CSharpKeyword"
  - "sbyte"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sbyte-Schlüsselwort [C#]"
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# sbyte (C#-Referenz)
Das `sbyte`\-Schlüsselwort kennzeichnet einen ganzzahligen Typ, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`sbyte`|\-128 bis 127|Ganze 8\-Bit\-Zahl mit Vorzeichen|<xref:System.SByte?displayProperty=fullName>|  
  
## Literale  
 Sie können auf diese Weise eine `sbyte`\-Variable deklarieren und initialisieren:  
  
```  
  
sbyte sByte1 = 127;  
```  
  
 In der vorangehenden Deklaration wird das Ganzzahlliteral 127 implizit von [int](../../../csharp/language-reference/keywords/int.md) in `sbyte` konvertiert.  Wenn der Bereich von `sbyte` vom Ganzzahlliteral überschritten wird, tritt ein Kompilierungsfehler auf.  
  
 Beim Aufrufen überladener Methoden muss eine Typumwandlung erfolgen.  Betrachten Sie z. B. die folgenden überladenen Methoden, die den `sbyte`\-Parameter und den [int](../../../csharp/language-reference/keywords/int.md)\-Parameter verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 Die Verwendung der `sbyte`\-Typumwandlung gewährleistet, dass der richtige Typ aufgerufen wird. Beispiel:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## Konvertierungen  
 Es erfolgt eine vordefinierte implizite Konvertierung von `sbyte` in [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Es ist nicht möglich, numerische Typen mit höherer Speichergröße, die keine Literale sind, implizit in `sbyte` zu konvertieren. \(Informationen zu den Speichergrößen ganzzahliger Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md).\)  Betrachten Sie beispielsweise die folgenden beiden `sbyte`\-Variablen `x` und `y`:  
  
```  
  
sbyte x = 10, y = 20;  
```  
  
 Die folgende Zuweisungsanweisung generiert einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig den Wert [int](../../../csharp/language-reference/keywords/int.md) annimmt.  
  
```  
  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 Um dieses Problem zu beheben, wandeln Sie den Ausdruck wie im folgenden Beispiel gezeigt um:  
  
```  
  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 Hier können jedoch die folgenden Anweisungen verwendet werden, bei denen die Zielvariable dieselbe oder eine höhere Speichergröße aufweist:  
  
```  
  
        sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Beachten Sie auch, dass Gleitkommatypen nicht implizit in `sbyte` konvertiert werden.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
  
        sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 Weitere Informationen zu arithmetischen Ausdrücken mit Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.SByte>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)