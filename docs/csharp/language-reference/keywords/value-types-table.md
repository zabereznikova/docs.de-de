---
title: Tabelle der Werttypen – C#-Referenz
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 98829f30c2c25c0710cf3fe044359d3c7538fe76
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424039"
---
# <a name="value-types-table-c-reference"></a>Tabelle der Werttypen (C#-Referenz)

In der folgenden Tabelle sind die Werttypen in C# angegeben:

|Werttyp|Kategorie|Typsuffix|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolesch||
|[byte](../builtin-types/integral-numeric-types.md)|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)
)||
|[decimal](decimal.md)|Numerisch, [Gleitkomma](floating-point-types-table.md)|M oder m|
|[double](double.md)|Numerisch, [Gleitkomma](floating-point-types-table.md)|D oder d|
|[enum](enum.md)|Enumeration||
|[float](float.md)|Numerisch, [Gleitkomma](floating-point-types-table.md)|F oder f|
|[int](../builtin-types/integral-numeric-types.md)|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|[long](../builtin-types/integral-numeric-types.md)|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)|L oder l|
|[sbyte](../builtin-types/integral-numeric-types.md)|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|[short](../builtin-types/integral-numeric-types.md)|Mit Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Eine benutzerdefinierte Struktur||
|[uint](../builtin-types/integral-numeric-types.md)|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)|U oder u|
|[ulong](../builtin-types/integral-numeric-types.md)|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU oder lu|
|[ushort](../builtin-types/integral-numeric-types.md)|Ohne Vorzeichen, numerisch, [integral](../builtin-types/integral-numeric-types.md)||

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
