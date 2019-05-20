---
title: Tabelle der Werttypen – C#-Referenz
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 7a2b61e7b699319bc57ff3fddcb712ef8e3c30fd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632855"
---
# <a name="value-types-table-c-reference"></a>Tabelle der Werttypen (C#-Referenz)

In der folgenden Tabelle sind die Werttypen in C# angegeben:

|Werttyp|Kategorie|Typsuffix|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolesch||
|[byte](byte.md)|Ohne Vorzeichen, numerisch, [integral](integral-types-table.md)||
|[char](char.md)|Ohne Vorzeichen, numerisch, [integral](integral-types-table.md)||
|[decimal](decimal.md)|Numerisch, [Gleitkomma](floating-point-types-table.md)|M oder m|
|[double](double.md)|Numerisch, [Gleitkomma](floating-point-types-table.md)|D oder d|
|[enum](enum.md)|Enumeration||
|[float](float.md)|Numerisch, [Gleitkomma](floating-point-types-table.md)|F oder f|
|[int](int.md)|Mit Vorzeichen, numerisch, [integral](integral-types-table.md)||
|[long](long.md)|Mit Vorzeichen, numerisch, [integral](integral-types-table.md)|L oder l|
|[sbyte](sbyte.md)|Mit Vorzeichen, numerisch, [integral](integral-types-table.md)||
|[short](short.md)|Mit Vorzeichen, numerisch, [integral](integral-types-table.md)||
|[struct](struct.md)|Eine benutzerdefinierte Struktur||
|[uint](uint.md)|Ohne Vorzeichen, numerisch, [integral](integral-types-table.md)|U oder u|
|[ulong](ulong.md)|Ohne Vorzeichen, numerisch, [integral](integral-types-table.md)|UL, Ul, uL, ul, LU, Lu, lU oder lu|
|[ushort](ushort.md)|Ohne Vorzeichen, numerisch, [integral](integral-types-table.md)||

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
- [Referenztabellen für Typen](reference-tables-for-types.md)
- [Tabelle für Standardwerte](default-values-table.md)
- [Werttypen](value-types.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](formatting-numeric-results-table.md)
