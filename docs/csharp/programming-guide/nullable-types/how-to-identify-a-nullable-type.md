---
title: 'Vorgehensweise: Identifizieren eines Nullable-Typs: C#-Programmierleitfaden'
ms.custom: seodec18
description: Erfahren Sie, wie Sie ermitteln, ob ein Typ ein Nullable-Werttyp oder eine Instanz eines Nullable-Werttyps ist.
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 15b1ffedf57648955ee5a004514841a5d140292b
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392605"
---
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a>Vorgehensweise: Identifizieren eines Nullable-Typs (C#-Programmierleitfaden)

Das folgende Beispiel zeigt, wie Sie bestimmen können, ob eine <xref:System.Type?displayProperty=nameWithType>-Instanz einen geschlossenen generischen Nullable-Werttyp darstellt, d.h. den <xref:System.Nullable%601?displayProperty=nameWithType>-Typ mit einem angegebenen Typparameter `T`:

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

Wie Sie im Beispiel sehen können, wird der Operator [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) verwendet, um ein <xref:System.Type?displayProperty=nameWithType>-Objekt zu erstellen.

Wenn Sie bestimmen möchten, ob eine Instanz einen Nullable-Werttyp aufweist, verwenden Sie nicht die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode, um eine <xref:System.Type>-Instanz abzurufen, die mit dem vorangehenden Code überprüft werden soll. Wenn Sie die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode in einer Instanz eines Nullable-Werttyps aufrufen, wird die Instanz in <xref:System.Object> [geschachtelt](using-nullable-types.md#boxing-and-unboxing). Da das Schachteln einer nicht-NULL-Instanz von einem Nullable-Werttyp dem Schachteln eines Werts des zugrunde liegenden Typs entspricht, gibt <xref:System.Object.GetType%2A> ein <xref:System.Type>-Objekt zurück, das den zugrunde liegenden Typ eines Nullable-Werttyps darstellt:

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

Verwenden Sie nicht den Operator [is](../../language-reference/keywords/is.md), um zu ermitteln, ob eine Instanz einem Nullable-Werttyp entspricht. Wie im folgenden Beispiel veranschaulicht wird, können Sie die Typen von Instanzen eines Nullable-Werttyps und den zugrunde liegenden Typ nicht mithilfe des `is`-Operators unterscheiden:

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

Sie können den Code verwenden, der im folgenden Beispiel dargestellt wird, um zu ermitteln, ob eine Instanz einen Nullable-Werttyp aufweist:

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](index.md)
- [Verwenden von Nullable-Werttypen](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
