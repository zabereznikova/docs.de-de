---
title: short (C#-Referenz)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f73189891ecb52b81cfc1861a19194113ab2c32
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="short-c-reference"></a>short (C#-Referenz)

`short` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.  
  
|Typ|Bereich|Größe|.NET Framework-Typ|  
|----------|-----------|----------|-------------------------|  
|`short`|–32.768 bis 32.767|Ganze 16-Bit-Zahl mit Vorzeichen|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Literale  

Sie können eine `short`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.  Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `short` befindet (sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf. 

Im folgenden Beispiel werden Ganzzahlen wie 1.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](../../../csharp/language-reference/keywords/int.md) in `short`-Werte konvertiert.  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals. Dezimale Literale haben kein Präfix.

Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt. 
 - C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.
 - C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu. Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.

Im Folgenden werden einige Beispiele veranschaulicht.

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a>Überladungsauflösung des Compiler

 Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden. Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `short` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 Die Verwendung der `short`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a>Konvertierungen  

 Es gibt eine vordefinierte implizite Konvertierung von `short` in [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Sie können numerische nonliteral-Typen einer größeren Speichergröße nicht implizit in `short` konvertieren (siehe [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) für die Speichergrößen ganzzahliger Typen). Betrachten Sie z.B. die folgenden beiden `short`-Variablen `x` und `y`:  
  
```csharp  
short x = 5, y = 12;  
```  
  
 Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig [int](../../../csharp/language-reference/keywords/int.md) ergibt.  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 Es ist jedoch auch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 Es gibt keine implizite Konvertierung von Gleitkommadatentypen zu `short`. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Int16>  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
