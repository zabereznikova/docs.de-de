---
title: Tabelle für implizite numerische Konvertierungen (C#-Referenz)
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: c3c0153a0ae3e07839822c8bb978b1a09277bd53
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188702"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabelle für implizite numerische Konvertierungen (C#-Referenz)

Folgende Tabelle veranschaulicht vordefinierte implizite Konvertierungen zwischen numerischen .NET-Typen.
  
|Von|Beschreibung|  
|----------|--------|  
|[sbyte](sbyte.md)|`short`, `int`, `long`, `float`, `double` oder `decimal`|  
|[byte](byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[short](short.md)|`int`, `long`, `float`, `double` oder `decimal`|  
|[ushort](ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[int](int.md)|`long`, `float`, `double` oder `decimal`|  
|[uint](uint.md)|`long`, `ulong`, `float`, `double` oder `decimal`|  
|[long](long.md)|`float`, `double`oder `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|  
|[float](float.md)|`double`|  
|[ulong](ulong.md)|`float`, `double`oder `decimal`|  
  
## <a name="remarks"></a>Hinweise  

- Jeder [integrale Typ](integral-types-table.md) kann implizit in einen beliebigen [Gleitkommatyp](floating-point-types-table.md) konvertiert werden.

- Bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` kann Präzision verloren gehen, aber keine Größe.  
  
- Es gibt keine impliziten Konvertierungen für den Typ `char`.  
  
- Es gibt keine impliziten Konvertierungen zwischen den Typen `float` und `double` und dem Typ `decimal`.  
  
- Ein Wert eines konstanten Ausdrucks vom Typ `int` (z.B. ein Wert, der von einem integralen Literal dargestellt wird) kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, solange er sich innerhalb des Bereichs des Zieltyps befindet:

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

Weitere Informationen über implizite Konvertierungen finden Sie im Abschnitt [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions) der [C#-Sprachspezifikation](../language-specification/index.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Tabelle ganzzahliger Typen](integral-types-table.md)
- [Tabelle für Gleitkommatypen](floating-point-types-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)
