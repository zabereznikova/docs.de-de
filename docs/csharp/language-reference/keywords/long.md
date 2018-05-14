---
title: long (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: f2bdc34400215ad24d5dcec2e1e9f314a01430d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="long-c-reference"></a>long (C#-Referenz)

`long` kennzeichnet einen Ganzzahltyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.  
  
|Typ|Bereich|Größe|.NET Framework-Typ|  
|----------|-----------|----------|-------------------------|  
|`long`|-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807|64-Bit-Ganzzahl mit Vorzeichen|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Literale 

Sie können eine `long`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen. 

Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `long`-Werten zugewiesen.  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals. Dezimale Literale haben kein Präfix. 

Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt. 
 - C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.
 - C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu. Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.

Im Folgenden werden einige Beispiele veranschaulicht.

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet. Das Suffix `L` kennzeichnet ein `long`. Im folgenden Beispiel wird das `L`-Suffix verwendet, um eine lange ganze Zahl anzugeben:
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  Sie können auch Kleinbuchstabe „l“ als Suffix verwenden. Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird. Verwenden Sie aus Gründen der Klarheit „L“.  
  
 Wenn Sie das Suffix `L` verwenden, wird der Typ des Ganzzahlliterals entweder als `long` oder [ulong](../../../csharp/language-reference/keywords/ulong.md) bestimmt, abhängig von seiner Größe. In diesem Fall ist er `long`, weil er kleiner als der Bereich von [ulong](../../../csharp/language-reference/keywords/ulong.md) ist.  
  
 Das Suffix wird häufig zum Aufrufen überladener Methoden verwendet. Die folgenden überladenen Methoden z.B. verfügen über Parameter des Typs `long` und [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 Das `L`-Suffix gewährleistet, dass die richtige Überladung aufgerufen wird:  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: 

1. [int](int.md)
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [ulong](../../../csharp/language-reference/keywords/ulong.md) 

Das Literal 4294967296 im vorhergehenden Beispiel ist vom Typ `long`, da er den Bereich von [uint](../../../csharp/language-reference/keywords/uint.md) überschreitet (Speichergrößen von ganzzahligen Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)).  
  
 Wenn Sie den `long`-Typ mit anderen ganzzahligen Typen im selben Ausdruck verwenden, wird der Ausdruck als `long` ausgewertet (oder [bool](../../../csharp/language-reference/keywords/bool.md) im Fall von relationalen oder booleschen Ausdrücken). Der folgende Ausdruck wird z.B. als `long` ausgewertet:  
  
```csharp  
898L + 88  
```  
  
 Weitere Informationen zu arithmetischen Ausdrücken mit gemischten Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
## <a name="conversions"></a>Konvertierungen  
 Es gibt eine vordefinierte implizite Konvertierung von `long` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md). Ansonsten muss eine Umwandlung verwendet werden. Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne explizite Umwandlung:  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Es gibt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `long`.  
  
 Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `long` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Int64>  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
