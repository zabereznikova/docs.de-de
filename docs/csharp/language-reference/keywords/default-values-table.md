---
title: Tabelle für Standardwerte (C#-Referenz)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a>Tabelle für Standardwerte (C#-Referenz)

In der folgenden Tabelle werden die Standardwerte von Werttypen gezeigt, die von den Standardkonstruktoren zurückgegeben werden. Standardkonstruktoren werden mit dem `new`-Operator wie folgt aufgerufen:

```csharp
int myInt = new int();
```

Die vorherige Anweisung hat den gleichen Effekt wie die folgende:

```csharp
int myInt = 0;
```

Denken Sie daran, dass die Verwendung von nicht initialisierten Variablen in C# nicht zulässig ist.

|Werttyp|Standardwert|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|Der Wert, der vom Ausdruck (E)0 erzeugt wird, bei dem E der Enumerationsbezeichner ist.|
|[float](float.md)|0.0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

## <a name="see-also"></a>Siehe auch
 [C#-Referenz](../index.md)  
 [C#-Programmierhandbuch](../../programming-guide/index.md)  
 [Tabelle der Werttypen](value-types-table.md)  
 [Werttypen](value-types.md)  
 [Tabelle integrierter Typen](built-in-types-table.md)  
 [Referenztabellen für Typen](reference-tables-for-types.md)
