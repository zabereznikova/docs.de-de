---
title: "ulong (C#-Referenz) | Microsoft Docs"
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
  - "ulong_CSharpKeyword"
  - "ulong"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ulong-Schlüsselwort [C#]"
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ulong (C#-Referenz)
Das `ulong`\-Schlüsselwort kennzeichnet einen ganzzahligen Typ, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`ulong`|0 bis 18,446,744,073,709,551,615|Vorzeichenlose 64\-Bit\-Ganzzahl|<xref:System.UInt64?displayProperty=fullName>|  
  
## Literale  
 Eine `ulong`\-Variable kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
  
ulong uLong = 9223372036854775808;  
```  
  
 Wenn ein Ganzzahlliteral kein Suffix besitzt, entspricht sein Typ dem ersten der folgenden Typen, mit dem sein Wert dargestellt werden kann: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), `ulong`.  Im obigen Beispiel ist es vom Typ `ulong`.  
  
 Suffixe können auch verwendet werden, um den ganzzahligen Typ gemäß den folgenden Regeln festzulegen:  
  
-   Bei Verwendung von L oder l entspricht der Typ des Ganzzahlliterals je nach dessen Größe entweder [long](../../../csharp/language-reference/keywords/long.md) oder `ulong`.  
  
    > [!NOTE]
    >  Der Kleinbuchstabe "l" kann als Suffix verwendet werden.  In diesem Fall wird jedoch eine Compilerwarnung generiert, da der Buchstabe "l" leicht mit der Ziffer "1" verwechselt werden kann. Verwenden Sie zur besseren Unterscheidung den Großbuchstaben "L".  
  
-   Bei Verwendung von `U` oder `u` entspricht der Typ des Ganzzahlliterals abhängig von der Größe entweder [uint](../../../csharp/language-reference/keywords/uint.md) oder `ulong`.  
  
-   Bei Verwendung von **UL**, **ul**, **Ul**, **uL**, **LU**, **lu**, **Lu** oder **lU** hat das Ganzzahlliteral den Typ `ulong`.  
  
     Durch die folgenden drei Anweisungen wird beispielsweise der Systemtyp `UInt64` ausgegeben, der dem `ulong`\-Alias entspricht:  
  
    ```  
    Console.WriteLine(9223372036854775808L.GetType());  
    Console.WriteLine(123UL.GetType());  
    Console.WriteLine((123UL + 456).GetType());  
    ```  
  
 Suffixe werden häufig beim Aufrufen überladener Methoden eingesetzt.  Betrachten Sie z. B. die folgenden überladenen Methoden, die den `ulong`\-Parameter und den [int](../../../csharp/language-reference/keywords/int.md)\-Parameter verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 Die Verwendung eines Suffixes mit dem `ulong`\-Parameter gewährleistet, dass der richtige Typ aufgerufen wird. Beispiel:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## Konvertierungen  
 Es erfolgt eine vordefinierte implizite Konvertierung von `ulong` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Es ist keine implizite Konvertierung von `ulong` in ganzzahlige Typen möglich.  Ohne explizite Typumwandlung wird durch die folgende Anweisung z. B. ein Kompilierungsfehler generiert:  
  
```  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 Es erfolgt eine vordefinierte implizite Konvertierung von [Byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `ulong`.  
  
 Darüber hinaus werden Gleitkommatypen nicht implizit in `ulong` konvertiert.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 Weitere Informationen über arithmetische Ausdrücke aus Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.UInt64>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)