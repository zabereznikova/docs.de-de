---
title: Tabelle für implizite numerische Konvertierungen – C#-Referenz
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 516505ccacfd2a8a5c275b0de033e1316fa06d3a
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661342"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabelle für implizite numerische Konvertierungen (C#-Referenz)

Folgende Tabelle veranschaulicht vordefinierte implizite Konvertierungen zwischen numerischen .NET-Typen.
  
|Von|Beschreibung|  
|----------|--------|  
|[sbyte](../builtin-types/integral-numeric-types.md)|`short`, `int`, `long`, `float`, `double` oder `decimal`|  
|[byte](../builtin-types/integral-numeric-types.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[short](../builtin-types/integral-numeric-types.md)|`int`, `long`, `float`, `double` oder `decimal`|  
|[ushort](../builtin-types/integral-numeric-types.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[int](../builtin-types/integral-numeric-types.md)|`long`, `float`, `double` oder `decimal`|  
|[uint](../builtin-types/integral-numeric-types.md)|`long`, `ulong`, `float`, `double` oder `decimal`|  
|[long](../builtin-types/integral-numeric-types.md)|`float`, `double`oder `decimal`|  
|[ulong](../builtin-types/integral-numeric-types.md)|`float`, `double`oder `decimal`|  
|[float](../builtin-types/floating-point-numeric-types.md)|`double`|  
  
## <a name="remarks"></a>Anmerkungen  

- Jeder [integrale Typ](../builtin-types/integral-numeric-types.md) kann implizit in einen beliebigen [Gleitkommatyp](../builtin-types/floating-point-numeric-types.md) konvertiert werden.

- Bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` kann Präzision verloren gehen, aber keine Größe.  
  
- Es gibt keine impliziten Konvertierungen in die Typen `char`, `byte` und `sbyte`.  

- Es gibt keine impliziten Konvertierungen aus den Typen `double` und `decimal`.
  
- Es gibt keine impliziten Konvertierungen zwischen dem Typ `decimal` und dem Typ `float` oder `double`.  
  
- Ein Wert eines konstanten Ausdrucks vom Typ `int` (z.B. ein Wert, der von einem integralen Literal dargestellt wird) kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, solange er sich innerhalb des Bereichs des Zieltyps befindet:

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

Weitere Informationen über implizite Konvertierungen finden Sie im Abschnitt [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions) der [C#-Sprachspezifikation](../language-specification/index.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Integrale Typen](../builtin-types/integral-numeric-types.md)
- [Tabelle für Gleitkommatypen](../builtin-types/floating-point-numeric-types.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)
