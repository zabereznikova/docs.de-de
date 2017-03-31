---
title: uint (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: fe4f7fcbbadee600e0ba6de70508312173d098ff
ms.lasthandoff: 03/13/2017

---
# <a name="uint-c-reference"></a>uint (C#-Referenz)
Das Schlüsselwort `uint` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.  
  
|Typ|Bereich|Größe|.NET Framework-Typ|  
|----------|-----------|----------|-------------------------|  
|`uint`|0 bis 4.294.967.295|32-Bit Ganzzahl ohne Vorzeichen|<xref:System.UInt32?displayProperty=fullName>|  
  
 **Hinweis** Der Typ `uint` ist nicht CLS-kompatibel. Verwenden Sie nach Möglichkeit `int`.  
  
## <a name="literals"></a>Literale  
 Sie können eine Variable des Typs `uint` wie im folgenden Beispiel deklarieren und initialisieren:  
  
```  
  
uint myUint = 4294967290;  
```  
  
 Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: [int](../../../csharp/language-reference/keywords/int.md), `uint`, [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md). In diesem Beispiel ist dies `uint`:  
  
```  
  
uint uInt1 = 123;  
```  
  
 Sie können auch das Suffix u oder U wie folgt verwenden:  
  
```  
  
uint uInt2 = 123U;  
```  
  
 Wenn Sie das Suffix `U` oder `u` verwenden, wird der Typ des Literals entweder als `uint` oder `ulong` bestimmt, gemäß des numerischen Werts des Literals. Zum Beispiel:  
  
```  
Console.WriteLine(44U.GetType());  
Console.WriteLine(323442434344U.GetType());  
```  
  
 Dieser Code zeigt `System.UInt32`, gefolgt von `System.UInt64` – die jeweiligen zugrundeliegenden Typen für `uint` und `ulong` –, da das zweite Literals zu groß ist, um von Typ `uint` gespeichert zu werden.  
  
## <a name="conversions"></a>Konvertierungen  
 Es gibt eine vordefinierte implizite Konvertierung von `uint` in [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md). Beispiel:  
  
```  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `uint`. Andernfalls müssen Sie eine Umwandlung verwenden. Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne Umwandlung:  
  
```  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `uint` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.UInt32>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
