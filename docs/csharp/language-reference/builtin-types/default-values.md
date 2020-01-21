---
title: 'Standardwerte der C#-Typen: C#-Referenz'
description: Informationen zu den Standardwerten der C#-Typen wie bool, char, int, float, double usw.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 2447db25e837cdcd6d67847b8677d7d44da551a9
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964872"
---
# <a name="default-values-of-c-types-c-reference"></a>Standardwerte der C#-Typen (C#-Referenz)

In der folgenden Tabelle werden die Standardwerte von C#-Typen gezeigt:

|Typ|Standardwert|
|---------|------------------|
|Verweistyp|`null`|
|Beliebiger [integrierter integraler numerischer Typ](integral-numeric-types.md)|0 (null)|
|Beliebiger [integrierter numerischer Gleitkommatyp](floating-point-numeric-types.md)|0 (null)|
|[bool](bool.md)|`false`|
|[char](char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.|
|[struct](../keywords/struct.md)|Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.|
|Ein [Werttyp, der NULL-Werte zulässt](nullable-value-types.md).|Eine Instanz, für die die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist. Dieser Standardwert wird auch als *NULL*-Wert eines Nullable-Werttyps bezeichnet.|

Verwenden Sie den [default-Operator](../operators/default.md), um wie im folgenden Beispiel den Standardwert eines Typs zu erzeugen:

```csharp
int a = default(int);
```

Ab C# 7.1 können Sie das [`default`-Literal](../operators/default.md#default-literal) verwenden, um eine Variable mit dem Standardwert des Typs zu initialisieren:

```csharp
int a = default;
```

Für eine Wertart generiert der implizite parameterlose Konstruktor auch den Standardwert des Typs, wie das folgende Beispiel zeigt:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

Wenn die <xref:System.Type?displayProperty=nameWithType>-Instanz zur Laufzeit einen Werttyp darstellt, können Sie die <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType>-Methode verwenden, um den parameterlosen Konstruktor aufzurufen, um den Standardwert des Typs abzurufen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Standardwerte](~/_csharplang/spec/variables.md#default-values)
- [Standardkonstruktoren](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md)
