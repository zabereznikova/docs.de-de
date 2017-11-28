---
title: "Tabelle für explizite numerische Konvertierungen (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7a366328035b205b93a50ff6d212a06576ee801
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Tabelle für explizite numerische Konvertierungen (C#-Referenz)
Eine explizite numerische Konvertierung wird verwendet, um einen numerischen Typ mithilfe eines Umwandlungausdrucks in einen beliebigen anderen numerischen Typ zu konvertieren, für den es keine implizite Konvertierung gibt. Die folgende Tabelle zeigt diese Konvertierungen.  
  
 Weitere Informationen darüber, wie Konvertierungen funktionieren, finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|Von|Beschreibung|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` oder `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` oder `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` oder `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`, `byte`, `short` oder `char`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` oder `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` oder `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` oder `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` oder `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte` oder `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`. `char` oder `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` oder `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` oder `double`|  
  
## <a name="remarks"></a>Hinweise  
  
-   Die explizite numerische Konvertierung kann zu einem Genauigkeitsverlust führen oder eine Ausnahme auslösen.  
  
-   Wenn Sie einen `decimal`-Wert in einen integralen Typ konvertieren, wird dieser Wert Richtung 0 (null) auf den nächsten Integralwert gerundet. Wenn der erzeugte Integralwert sich außerhalb des Bereichs des Zieltyps befindet, wird eine <xref:System.OverflowException> ausgelöst.  
  
-   Wenn Sie einen `double`- oder `float`-Wert konvertieren, wird er Wert abgeschnitten. Wenn der erzeugte Integralwert sich außerhalb des Bereichs des Zielwerts befindet, hängt das Ergebnis vom Kontext der Überlaufprüfung ab. In einem geprüften Kontext wird eine `OverflowException` ausgelöst, während das Ergebnis in einem ungeprüften Kontext ein nicht angegebener Wert des Zieltyps ist.  
  
-   Wenn Sie `double` in `float` konvertieren, wird der `double`-Wert auf den nächsten `float`-Wert gerundet. Wenn der `double`-Wert zu klein oder zu groß ist, um in den Zieltyp zu passen, ist das Ergebnis 0 (null) oder unendlich.  
  
-   Wenn Sie `float` oder `double` in `decimal` konvertieren, wird der Quellwert in eine `decimal`-Darstellung konvertiert und bei Bedarf auf die nächste Zahl nach der achtundzwanzigsten Dezimalstelle gerundet. Je nach Wert des Quellwerts kann eines der folgenden Ergebnisse auftreten:  
  
    -   Wenn der Quellwert zu klein ist, als dass er als `decimal` dargestellt werden könnte, ist das Ergebnis 0 (null).  
  
    -   Wenn der Quellwert NaN (nicht numerisch), unendlich oder zu groß ist, um als `decimal` dargestellt zu werden, wird eine `OverflowException` ausgelöst.  
  
-   Wenn Sie `decimal` in `float` oder `double` konvertieren, wird der `decimal`-Wert auf den nächsten `double`- oder `float`-Wert konvertiert.  
  
 Weitere Informationen zu expliziten Konvertierungen finden Sie unter „Explicit“ in der C#-Sprachspezifikation. Weitere Informationen zum Zugriff auf die Spezifikation finden Sie in der [C#-Sprachspezifikation](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [()-Operator](../../../csharp/language-reference/operators/invocation-operator.md)  
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
