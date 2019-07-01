---
title: Tabelle für Standardwerte – C#-Referenz
ms.custom: seodec18
description: Erfahren Sie, was die Standardwerte der C#-Werttypen sind.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: dfab5107d4a0ad14c3ffbfc6a5f3c4317b44d17c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424221"
---
# <a name="default-values-table-c-reference"></a>Tabelle für Standardwerte (C#-Referenz)

In der folgenden Tabelle werden die Standardwerte von [Werttypen](value-types.md) gezeigt.

|Werttyp|Standardwert|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](../builtin-types/integral-numeric-types.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.|
|[float](float.md)|0.0F|
|[int](../builtin-types/integral-numeric-types.md)|0|
|[long](../builtin-types/integral-numeric-types.md)|0L|
|[sbyte](../builtin-types/integral-numeric-types.md)|0|
|[short](../builtin-types/integral-numeric-types.md)|0|
|[struct](struct.md)|Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.|
|[uint](../builtin-types/integral-numeric-types.md)|0|
|[ulong](../builtin-types/integral-numeric-types.md)|0|
|[ushort](../builtin-types/integral-numeric-types.md)|0|

## <a name="remarks"></a>Anmerkungen

Sie können keine nicht initialisierten Variablen in C# verwenden. Sie können eine Variable mit dem Standardwert des Typs initialisieren. Sie können den Standardwert eines Typs verwenden, um den Standardwert des [optionalen Arguments](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) einer Methode festzulegen.

Verwenden Sie den [Standardwertausdruck](../../programming-guide/statements-expressions-operators/default-value-expressions.md), um den Standardwert eines Typs wie im folgenden Beispiel zu erzeugen:

```csharp
int a = default(int);
```

Ab C# 7.1 können Sie das [`default`-Literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) verwenden, um eine Variable mit dem Standardwert des Typs zu initialisieren:

```csharp
int a = default;
```

Sie können auch den parameterlosen Konstruktor oder den impliziten parameterlosen Konstruktor verwenden, um den Standardwert eines Werttyps zu erzeugen. Dies wird im folgenden Beispiel veranschaulicht. Weitere Informationen zu Konstruktoren finden Sie im Artikel [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md).

```csharp
int a = new int();
```

Der Standardwert eines beliebigen [Verweistyps](reference-types.md) ist `null`. Der Standardwert eines [Nullable-Typs](../../programming-guide/nullable-types/index.md) ist eine Instanz, deren <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Werttypen](value-types.md)
- [Tabelle der Werttypen](value-types-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
