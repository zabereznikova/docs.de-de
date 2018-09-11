---
title: Tabelle ganzzahliger Typen (C#-Referenz)
description: Übersicht über die ganzzahligen Typen in C#
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 4ac16d185a52cdb03fcb22f57ebf7506f2fb2745
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078847"
---
# <a name="integral-types-table-c-reference"></a>Tabelle ganzzahliger Typen (C#-Referenz)

Die folgende Tabelle enthält Größe und Bereich der integralen Typen, die eine Teilmenge der einfachen Typen bilden.  
  
|Typ|Bereich|Größe|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|–128 bis 127|Ganze 8-Bit-Zahl mit Vorzeichen|  
|[byte](byte.md)|0 bis 255|8-Bit-Ganzzahl ohne Vorzeichen|  
|[char](char.md)|U+0000 bis U+ffff|Ein Unicode-Zeichen (16 Bit)|  
|[short](short.md)|–32.768 bis 32.767|Ganze 16-Bit-Zahl mit Vorzeichen|  
|[ushort](ushort.md)|0 bis 65.535|16-Bit-Ganzzahl ohne Vorzeichen|  
|[int](int.md)|-2,147,483,648 bis 2,147,483,647|Eine 32-Bit-Ganzzahl mit Vorzeichen|  
|[uint](uint.md)|0 bis 4.294.967.295|32-Bit Ganzzahl ohne Vorzeichen|  
|[long](long.md)|-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807|64-Bit-Ganzzahl mit Vorzeichen|  
|[ulong](ulong.md)|0 bis 18.446.744.073.709.551.615|64-Bit-Ganzzahl ohne Vorzeichen|  

## <a name="remarks"></a>Hinweise
  
Wenn der von einem Integer-Literal dargestellte Wert <xref:System.UInt64.MaxValue?displayProperty=nameWithType> überschreitet, tritt der Compilerfehler [CS1021](../../misc/cs1021.md) auf.

Mit der <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Klasse können Sie eine beliebig große ganze Zahl mit Vorzeichen darstellen.
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Referenztabellen für Typen](reference-tables-for-types.md)
- [Tabelle für Gleitkommatypen](floating-point-types-table.md)
- [Tabelle für Standardwerte](default-values-table.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](formatting-numeric-results-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
