---
title: "int (C#-Referenz) | Microsoft Docs"
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
  - "int_CSharpKeyword"
  - "int"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "int-Schlüsselwort [C#]"
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# int (C#-Referenz)
Das `int`\-Schlüsselwort kennzeichnet einen ganzzahligen Typ, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|Standardwert|  
|---------|-------------|-----------|-------------------------|------------------|  
|`int`|\-2.147.483.648 bis 2.147.483.647|Ganze 32\-Bit\-Zahl mit Vorzeichen|<xref:System.Int32?displayProperty=fullName>|0|  
  
## Literale  
 Eine Variable vom Typ `int` kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
  
int i = 123;  
```  
  
 Wenn ein Ganzzahlliteral kein Suffix besitzt, entspricht sein Typ dem ersten der folgenden Typen, mit dem sein Wert dargestellt werden kann: `int`, [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md).  In diesem Beispiel entspricht der Typ `int`.  
  
## Konvertierungen  
 Es erfolgt eine vordefinierte implizite Konvertierung von `int` in [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  Beispiel:  
  
```  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 Es erfolgt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `int`.  Ohne Umwandlung verursacht die folgende Anweisung beispielsweise einen Kompilierungsfehler:  
  
```  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 Beachten Sie auch, dass Gleitkommatypen nicht implizit in `int` konvertiert werden.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
  
        int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 Weitere Informationen zu arithmetischen Ausdrücken aus Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Int32>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)