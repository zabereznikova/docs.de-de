---
title: Tabelle der Werttypen – C#-Referenz
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 2e2897ff647140b58b3a1812e153a44a6fcdaef7
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859559"
---
# <a name="value-types-table-c-reference"></a>Tabelle der Werttypen (C#-Referenz)

In der folgenden Tabelle sind die Werttypen in C# angegeben:

|Werttyp|Kategorie|Typsuffix|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolesch||
|`byte`|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)
|`decimal`|Numerisch, [Gleitkomma](../builtin-types/floating-point-numeric-types.md)|M oder m|
|`double`|Numerisch, [Gleitkomma](../builtin-types/floating-point-numeric-types.md)|D oder d|
|[enum](enum.md)|Enumeration||
|`float`|Numerisch, [Gleitkomma](../builtin-types/floating-point-numeric-types.md)|F oder f|
|`int`|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|`long`|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)|L oder l|
|`sbyte`|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|`short`|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Eine benutzerdefinierte Struktur||
|`uint`|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)|U oder u|
|`ulong`|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU oder lu|
|`ushort`|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||

## <a name="remarks"></a>Anmerkungen

Sie verwenden ein Typsuffix zum Angeben eines numerischen Literaltyps. Beispiel:

```csharp
decimal a = 0.1M;
```

Wenn ein [numerisches Ganzzahlliteral](~/_csharplang/spec/lexical-structure.md#integer-literals) kein Suffix besitzt, enthält es den ersten der folgenden Typen, in dem sein Wert dargestellt werden kann: `int`, `uint`, `long`, `ulong`.

Wenn ein [reales Ganzzahlliteral](~/_csharplang/spec/lexical-structure.md#real-literals) kein Suffix besitzt, ist es vom Typ `double`.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Tabelle für Standardwerte](default-values-table.md)
- [Werttypen](value-types.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](formatting-numeric-results-table.md)
