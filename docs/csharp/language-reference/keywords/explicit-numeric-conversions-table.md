---
title: Tabelle für explizite numerische Konvertierungen (C#-Referenz)
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 22bb2117e7b78596e1fb6af63584f51b066564c9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47208236"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Tabelle für explizite numerische Konvertierungen (C#-Referenz)

Folgende Tabelle veranschaulicht vordefinierte explizite Konvertierungen zwischen numerischen .NET-Typen, für die es keine [implizite Konvertierung](implicit-numeric-conversions-table.md) gibt.

|Von|Beschreibung|  
|----------|--------|  
|[sbyte](sbyte.md)|`byte`, `ushort`, `uint`, `ulong` oder `char`|  
|[byte](byte.md)|`sbyte` oder `char`|  
|[short](short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` oder `char`|  
|[ushort](ushort.md)|`sbyte`, `byte`, `short` oder `char`|  
|[int](int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` oder `char`|  
|[uint](uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` oder `char`|  
|[long](long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` oder `char`|  
|[ulong](ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` oder `char`|  
|[char](char.md)|`sbyte`, `byte`oder `short`|  
|[float](float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`. `char` oder `decimal`|  
|[double](double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` oder `decimal`|  
|[decimal](decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` oder `double`|  
  
## <a name="remarks"></a>Hinweise  
  
- Die explizite numerische Konvertierung kann zu einem Genauigkeitsverlust führen oder eine Ausnahme auslösen, in der Regel <xref:System.OverflowException>.  

- Wenn Sie einen Wert von einem integralen Typ in einen anderen integralen Typ konvertieren, ist das Ergebnis vom [Kontext der Überlaufprüfung](checked-and-unchecked.md) abhängig. Die Konvertierung in einem geprüften Kontext ist erfolgreich, wenn der Quellwert sich innerhalb des Bereichs des Zieltyps befindet. Andernfalls wird eine <xref:System.OverflowException> ausgelöst. In einem ungeprüften Kontext ist die Konvertierung immer erfolgreich, und sie verläuft wie folgt:

  - Wenn der Quelltyp größer als der Zieltyp ist, wird der Quellwert abgeschnitten, indem die wichtigsten „zusätzlichen“ Teile verworfen werden. Das Ergebnis wird dann als Wert des Zieltyps behandelt.

  - Wenn der Quelltyp kleiner als der Zieltyp ist, wird der Quellwert entweder mit Vorzeichen oder Nullen (0) erweitert, sodass er die gleiche Größe wie der Zieltyp aufweist. Die Vorzeichenerweiterung wird verwendet, wenn der Quelltyp mit einem Vorzeichen versehen ist. Die Erweiterung mit Nullen (0) wird verwendet, wenn der Quelltyp mit keinem Vorzeichen versehen ist. Das Ergebnis wird dann als Wert des Zieltyps behandelt.

  - Wenn der Quelltyp die gleiche Größe wie der Zieltyp aufweist, wird der Quellwert als Wert vom Zieltyp behandelt.
  
- Wenn Sie einen `decimal`-Wert in einen integralen Typ konvertieren, wird dieser Wert Richtung 0 (null) auf den nächsten Integralwert gerundet. Wenn der erzeugte Integralwert sich außerhalb des Bereichs des Zieltyps befindet, wird eine <xref:System.OverflowException> ausgelöst.  
  
- Wenn Sie einen `double`- oder`float`-Wert in einen integralen Typ konvertieren, wird dieser Wert Richtung 0 (null) auf den nächsten Integralwert gerundet. Wenn der resultierende Integralwert sich außerhalb des Bereichs des Zieltyps befindet, hängt das Ergebnis vom [Kontext der Überlaufprüfung](checked-and-unchecked.md) ab. In einem geprüften Kontext wird eine <xref:System.OverflowException> ausgelöst, während das Ergebnis in einem ungeprüften Kontext ein nicht angegebener Wert des Zieltyps ist.  
  
- Wenn Sie `double` in `float` konvertieren, wird der `double`-Wert auf den nächsten `float`-Wert gerundet. Wenn der `double`-Wert zu klein oder zu groß ist, um in den Zieltyp zu passen, ist das Ergebnis 0 (null) oder unendlich.  
  
- Wenn Sie `float` oder `double` in `decimal` konvertieren, wird der Quellwert in eine `decimal`-Darstellung konvertiert und bei Bedarf auf die nächste Zahl nach der achtundzwanzigsten Dezimalstelle gerundet. Je nach Wert des Quellwerts kann eines der folgenden Ergebnisse auftreten:  

  - Wenn der Quellwert zu klein ist, als dass er als `decimal` dargestellt werden könnte, ist das Ergebnis 0 (null).  

  - Wenn der Quellwert NaN (nicht numerisch), unendlich oder zu groß ist, um als `decimal` dargestellt zu werden, wird eine <xref:System.OverflowException> ausgelöst.  
  
- Wenn Sie `decimal` in `float` oder `double` konvertieren, wird der `decimal`-Wert auf den nächsten `double`- oder `float`-Wert konvertiert.  
  
 Weitere Informationen über explizite Konvertierungen finden Sie im Abschnitt [Explicit conversions (Explizite Konvertierungen)](/dotnet/csharp/language-reference/language-specification/conversions#explicit-conversions) der [C#-Sprachspezifikation](../language-specification/index.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)
- [()-Operator](../operators/invocation-operator.md)
- [Tabelle ganzzahliger Typen](integral-types-table.md)
- [Tabelle für Gleitkommatypen](floating-point-types-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md)
