---
description: Informationen zu nicht verwalteten Typen in C#
title: 'Nicht verwaltete Typen: C#-Verweis'
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 4374872af13c94e1a1af6b9f2c431f076c6f7dff
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471798"
---
# <a name="unmanaged-types-c-reference"></a>Nicht verwaltete Typen (C#-Verweis)

Ein Typ ist ein **nicht verwalteter Typ** , wenn es sich um einen der folgenden Typen handelt:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` oder `bool`
- Beliebiger [Enumerationstyp](enum.md)
- Beliebiger [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- Jeder benutzerdefinierte [Strukturtyp](struct.md), der nur Felder mit nicht verwalteten Typen enthält und – in C# 7.3 und früher – kein konstruierter Typ ist (ein konstruierter Typ ist ein Typ, der mindestens ein Typargument enthält)

Ab C# 7.3 können Sie die [`unmanaged`-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) verwenden, um anzugeben, dass ein Typparameter ein nicht verwalteter Nicht-Nullable-Nichtzeigertyp ist.

Ab C# 8.0 ist ein *konstruierter* Strukturtyp, der Felder mit nicht verwalteten Typen enthält, ebenfalls nicht verwaltet, wie das folgende Beispiel zeigt:

[!code-csharp[unmanaged constructed types](snippets/shared/UnmanagedTypes.cs#ProgramExample)]

Eine generische Struktur kann als Quelle sowohl für nicht verwaltete als auch für verwaltete konstruierte Typen dienen. Das oben stehende Beispiel definiert die generische Struktur `Coords<T>` und zeigt Beispiele nicht verwalteter konstruierter Typen. Ein Beispiel für einen verwalteten Typ ist `Coords<object>`. Der Typ ist verwaltet, weil er Felder des Typs `object` enthält, der verwaltet ist. Wenn *alle* konstruierten Typen nicht verwaltet sein sollen, verwenden Sie die `unmanaged`-Einschränkung in der Definition einer generischen Struktur:

[!code-csharp[unmanaged constraint in type definition](snippets/shared/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Memory- und Span-bezogene Typen](../../../standard/memory-and-spans/index.md)
- [sizeof (Operator)](../operators/sizeof.md)
- [stackalloc](../operators/stackalloc.md)
