---
title: sbyte (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
ms.openlocfilehash: 1dca23c4a4216f1edc79b7701a002a28652aed26
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577397"
---
# <a name="sbyte-c-reference"></a>sbyte (C#-Referenz)

`sbyte` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.  
  
|Typ|Bereich|Größe|.NET-Typ|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|–128 bis 127|Ganze 8-Bit-Zahl mit Vorzeichen|<xref:System.SByte?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Literale  

Sie können eine `sbyte`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen. 

Im folgenden Beispiel werden Ganzzahlen wie -102, die als dezimale, hexadezimale und binäre Literale dargestellt werden, aus [int](../../../csharp/language-reference/keywords/int.md) in `sbyte`-Werte konvertiert.    
  
[!code-csharp[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]  

> [!NOTE] 
> Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals. Dezimale Literale haben kein Präfix.

Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt. 
 - C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.
 - C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu. Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.

 Im Folgenden werden einige Beispiele veranschaulicht.

[!code-csharp[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]  

Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `sbyte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf. Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md). Dies bedeutet, dass in diesem Beispiel die numerischen Literale `0x9A` und `0b10011010` als 32-Bit Ganzzahlen mit Vorzeichen mit einem Wert von 156 interpretiert werden, was <xref:System.SByte.MaxValue?displayProperty=nameWithType> übersteigt. Aus diesem Grund wird der Umwandlungsoperator benötigt, und die Zuordnung muss in einem [unchecked](unchecked.md) Kontext erfolgen. 

## <a name="compiler-overload-resolution"></a>Überladungsauflösung des Compiler

 Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden. Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `sbyte` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 Die Verwendung der `sbyte`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a>Konvertierungen  
 Es gibt eine vordefinierte implizite Konvertierung von `sbyte` in [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Sie können numerische nonliteral-Typen einer größeren Speichergröße nicht implizit zu `sbyte` konvertieren (siehe [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) für die Speichergrößen ganzzahliger Typen). Betrachten Sie z.B. die folgenden beiden `sbyte`-Variablen `x` und `y`:  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig [int](../../../csharp/language-reference/keywords/int.md) ergibt.  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 Wandeln Sie den Ausdruck wie im folgenden Beispiel um, um das Problem zu beheben:  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `sbyte` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.SByte>  
- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
