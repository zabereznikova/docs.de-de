---
title: "ushort (C#-Referenz) | Microsoft Docs"
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
  - "ushort"
  - "ushort_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ushort-Schlüsselwort [C#]"
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ushort (C#-Referenz)
Das `ushort`\-Schlüsselwort kennzeichnet einen ganzzahligen Datentyp, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`ushort`|0 bis 65.535|Ganze 16\-Bit\-Zahl ohne Vorzeichen|<xref:System.UInt16?displayProperty=fullName>|  
  
## Literale  
 Eine `ushort`\-Variable kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
  
ushort myShort = 65535;  
```  
  
 In der vorangehenden Deklaration wird das Ganzzahlliteral `65535` implizit von [int](../../../csharp/language-reference/keywords/int.md) in `ushort` konvertiert.  Wenn der Bereich von `ushort` vom Ganzzahlliteral überschritten wird, tritt ein Kompilierungsfehler auf.  
  
 Beim Aufrufen überladener Methoden muss eine Typumwandlung erfolgen.  Betrachten Sie z. B. die folgenden überladenen Methoden, die den `ushort`\-Parameter und den [int](../../../csharp/language-reference/keywords/int.md)\-Parameter verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
  
 Die Verwendung der `ushort`\-Typumwandlung gewährleistet, dass der richtige Typ aufgerufen wird. Beispiel:  
  
```  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## Konvertierungen  
 Es erfolgt eine vordefinierte implizite Konvertierung von `ushort` in [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Es erfolgt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `ushort`.  Andernfalls muss für eine explizite Konvertierung eine Typumwandlung erfolgen.  Betrachten Sie z. B. die beiden folgenden `ushort`\-Variablen `x` und `y`:  
  
```  
  
ushort x = 5, y = 12;  
```  
  
 Die folgende Zuweisungsanweisung generiert einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig den Wert `int` annimmt.  
  
```  
  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Verwenden Sie zur Problembehebung eine Typumwandlung:  
  
```  
  
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Hier können jedoch die folgenden Anweisungen verwendet werden, bei denen die Zielvariable dieselbe oder eine höhere Speichergröße aufweist:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Beachten Sie auch, dass Gleitkommatypen nicht implizit in `ushort` konvertiert werden.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Weitere Informationen zu arithmetischen Ausdrücken mit Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.UInt16>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)