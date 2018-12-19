---
title: Tabelle integrierter Typen – C#-Referenz
ms.custom: seodec18
description: Schlüsselwörter für integrierte C#-Typen
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: fae0cedfe8bf675dceb9cb9d5835d923cae8b4ab
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235624"
---
# <a name="built-in-types-table-c-reference"></a>Tabelle integrierter Typen (C#-Referenz)

Die folgende Tabelle zeigt die Schlüsselwörter für integrierte C#-Typen, bei denen es sich um Aliase der vordefinierten Typen im <xref:System>-Namespace handelt.  
  
|C#-Typ|.NET-Typ|  
|--------------|-------------------------|  
|[bool](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>Hinweise

Mit Ausnahme von `object` und `string` werden alle in der Tabelle enthaltenen Typen als einfache Typen bezeichnet.  
  
C#-Typschlüsselwörter und ihre Aliase sind austauschbar. So können Sie beispielsweise eine ganzzahlige Variable mit einer der beiden folgenden Deklarationen angeben:  

```csharp
int x = 123;
System.Int32 y = 123;
```

Verwenden Sie den Operator [typeof](typeof.md), um die <xref:System.Type?displayProperty=nameWithType>-Instanz abzurufen, die den angegebenen Typ darstellt:

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

- [C#-Referenz](../../../csharp/language-reference/index.md)
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Referenztabellen für Typen](reference-tables-for-types.md)
- [Werttypen](value-types.md)
- [Verweistypen](reference-types.md)
- [Tabelle für Standardwerte](default-values-table.md)
- [dynamic](dynamic.md)
