---
title: long (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c28c8308d7ed32f7240f56113a77a0794cb1ba62
ms.lasthandoff: 03/13/2017

---
# <a name="long-c-reference"></a>long (C#-Referenz)
Das Schlüsselwort `long` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.  
  
|Typ|Bereich|Größe|.NET Framework-Typ|  
|----------|-----------|----------|-------------------------|  
|`long`|–9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807|64-Bit-Ganzzahl mit Vorzeichen|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a>Literale  
 Sie können eine `long`-Variable wie im folgenden Beispiel deklarieren und initialisieren:  
  
```  
  
long long1 = 4294967296;  
```  
  
 Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), `long` und [ulong](../../../csharp/language-reference/keywords/ulong.md). Im vorhergehenden Beispiel ist der Typ `long`, da er den Bereich von [uint](../../../csharp/language-reference/keywords/uint.md) überschreitet (Speichergrößen von ganzzahligen Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)).  
  
 Sie können auch das Suffix „L“ mit dem Typ `long` wie folgt verwenden:  
  
```  
  
long long2 = 4294967296L;  
```  
  
 Wenn Sie das Suffix „L“ verwenden, wird der Typ des Ganzzahlliterals entweder als `long` oder [ulong](../../../csharp/language-reference/keywords/ulong.md) bestimmt, gemäß seiner Größe. In diesem Fall ist er `long`, weil er kleiner als der Bereich von [ulong](../../../csharp/language-reference/keywords/ulong.md) ist.  
  
 Das Suffix wird häufig beim Aufrufen überladener Methoden verwendet. Betrachten Sie z.B. die folgenden überladenen Methoden, die Parameter `long` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 Die Verwendung des Suffixes „L“ gewährleistet, dass der richtige Typ aufgerufen wird, z.B.:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 Sie können den Typ `long` mit anderen numerischen ganzzahligen Typen im selben Ausdruck verwenden, wobei in diesem Fall der Ausdruck als `long` (oder [bool](../../../csharp/language-reference/keywords/bool.md) im Fall von relationalen oder booleschen Ausdrücken) ausgewertet wird. Der folgende Ausdruck wird z.B. als `long` ausgewertet:  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  Sie können auch Kleinbuchstabe „l“ als Suffix verwenden. Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird. Verwenden Sie aus Gründen der Klarheit „L“.  
  
 Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
## <a name="conversions"></a>Konvertierungen  
 Es gibt eine vordefinierte implizite Konvertierung von `long` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md). Ansonsten muss eine Umwandlung verwendet werden. Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne explizite Umwandlung:  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Es gibt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `long`.  
  
 Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `long` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```  
  
      long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Int64></xref:System.Int64>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
