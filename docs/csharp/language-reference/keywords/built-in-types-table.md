---
title: Tabelle integrierter Typen – C#-Referenz
description: Schlüsselwörter für integrierte C#-Typen
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 1836458972c453b733287e58e783f32892d27fde
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964386"
---
# <a name="built-in-types-table-c-reference"></a>Tabelle integrierter Typen (C#-Referenz)

Die folgende Tabelle zeigt die Schlüsselwörter für integrierte C#-Typen, bei denen es sich um Aliase der vordefinierten Typen im <xref:System>-Namespace handelt:

|C#-Typ|.NET-Typ|  
|--------------|-------------------------|  
|[bool](../builtin-types/bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](../builtin-types/char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](../builtin-types/reference-types.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](../builtin-types/reference-types.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>Hinweise

Mit Ausnahme von `object` und `string` werden alle in der Tabelle enthaltenen Typen als einfache Typen bezeichnet.

Die .NET-Typen und deren Aliase für C#-Typschlüsselwörter sind austauschbar. So können Sie beispielsweise eine ganzzahlige Variable mit einer der beiden folgenden Deklarationen angeben:

```csharp
int x = 123;
System.Int32 y = 123;
```

Verwenden Sie den Operator [typeof](../operators/type-testing-and-cast.md#typeof-operator), um die <xref:System.Type?displayProperty=nameWithType>-Instanz abzurufen, die den angegebenen Typ darstellt:

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Werttypen](value-types.md)
- [Verweistypen](reference-types.md)
- [Standardwerte der C#-Typen](../builtin-types/default-values.md)
- [dynamic](../builtin-types/reference-types.md#the-dynamic-type)
