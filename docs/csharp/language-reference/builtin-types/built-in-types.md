---
title: 'Integrierte Typen: C#-Referenz'
description: Hier erfahren Sie mehr über in C# integrierte Werte und Verweistypen.
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389494"
---
# <a name="built-in-types-c-reference"></a>Integrierte Typen (C#-Referenz)

In der folgenden Tabelle werden die in C# integrierten [Werttypen](value-types.md) aufgelistet:

|C#-Typschlüsselwort|.NET-Typ|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

In der folgenden Tabelle werden die in C# integrierten [Verweistypen](../keywords/reference-types.md) aufgelistet:

|C#-Typschlüsselwort|.NET-Typ|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

In den obigen Tabellen ist jedes C#-Typschlüsselwort aus der linken Spalte ein Alias für den entsprechenden .NET-Typ. Sie können synonym verwendet werden. In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:

```csharp
int a = 123;
System.Int32 b = 123;
```

Das Schlüsselwort [`void`](void.md) markiert das Fehlen eines Typs. Sie können es als Rückgabetyp einer Methode verwenden, die keinen Wert zurückgibt.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Standardwerte der C#-Typen](default-values.md)
- [`dynamic`Schlüsselwort](reference-types.md#the-dynamic-type)
