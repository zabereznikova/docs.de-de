---
title: byte (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: ee70b7c804423a35e2db3fe20ac4b66d8d1b98e2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505094"
---
# <a name="byte-c-reference"></a>byte (C#-Referenz)

`byte` kennzeichnet einen ganzzahligen Typ, der Werte anhand der folgenden Tabelle speichert.  
  
|Typ|Bereich|Größe|.NET-Typ|  
|----------|-----------|----------|-------------------------|  
|`byte`|0 bis 255|8-Bit-Ganzzahl ohne Vorzeichen|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Literale  

 Sie können eine `byte`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen. Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `byte` befindet (sprich, wenn es kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Byte.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden ganze Zahlen, die gleich 201 sind und von dezimalen, hexadezimalen und binären Literalen dargestellt werden, implizit von [int](../../../csharp/language-reference/keywords/int.md)- in `byte`-Werte konvertiert.    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals. Dezimale Literale haben kein Präfix.

Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt. 
 - C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.
 - C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu. Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.

Im Folgenden werden einige Beispiele veranschaulicht.

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a>Konvertierungen  
 Es gibt eine vordefinierte implizite Konvertierung von `byte` in [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Sie können nicht literale numerische Typen mit einer größeren Speichergröße nicht implizit zu `byte` konvertieren. Weitere Informationen zu Speichergrößen ganzzahliger Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md). Betrachten Sie z.B. die folgenden beiden `byte`-Variablen `x` und `y`:  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 Die folgende Zuweisungsanweisung erzeugt einen Compilerfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkommadatentypen in `byte` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden. Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `byte` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 Die Verwendung der `byte`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 Weitere Informationen zu arithmetischen Ausdrücken mit gemischten Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  

- <xref:System.Byte>  
- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
