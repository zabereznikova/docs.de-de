---
title: 'Vorgehensweise: Identifizieren eines Nullable-Typs (C#-Programmierhandbuch)'
description: Erfahren Sie, wie Sie ermitteln, ob ein Typ ein Nullable-Typ oder eine Instanz eines Nullable-Typs ist.
ms.date: 09/24/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f9957568d3c68f60cc9286718be9f5a496f876e6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47400542"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Vorgehensweise: Identifizieren eines Nullable-Typs (C#-Programmierhandbuch)

Das folgende Beispiel zeigt, wie Sie bestimmen können, ob eine <xref:System.Type?displayProperty=nameWithType>-Instanz einen geschlossenen generischen Nullable-Typ darstellt, d.h. den <xref:System.Nullable%601?displayProperty=nameWithType>-Typ mit einem angegebenen Typparameter `T`:

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

Wie Sie im Beispiel sehen können, wird der Operator [typeof](../../language-reference/keywords/typeof.md) verwendet, um ein <xref:System.Type?displayProperty=nameWithType>-Objekt zu erstellen.  
  
Wenn Sie bestimmen möchten, ob eine Instanz einen Nullable-Typ aufweist, verwenden Sie nicht die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode, um eine <xref:System.Type>-Instanz abzurufen, die mit dem vorangehenden Code überprüft werden soll. Wenn Sie die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode in einer Instanz eines Nullable-Typs aufrufen, wird die Instanz in <xref:System.Object> [geschachtelt](using-nullable-types.md#boxing-and-unboxing). Da das Schachteln einer nicht-NULL-Instanz von einem Nullable-Typ dem Schachteln eines Werts des zugrunde liegenden Typs entspricht, gibt <xref:System.Object.GetType%2A> ein <xref:System.Type>-Objekt zurück, das den zugrunde liegenden Typ eines Nullable-Typs darstellt:

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

Verwenden Sie nicht den Operator [is](../../language-reference/keywords/is.md), um zu ermitteln, ob eine Instanz einem Nullable-Typ entspricht. Wie im folgenden Beispiel veranschaulicht wird, können Sie die Typen von Instanzen eines Nullable-Typs und den zugrunde liegenden Typ nicht mithilfe des `is`-Operators unterscheiden:

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

Sie können den Code verwenden, der im folgenden Beispiel dargestellt wird, um zu ermitteln, ob eine Instanz einen Nullable-Typ aufweist:

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a>Siehe auch

- [Nullable-Typen](index.md)  
- [Using nullable types (Verwenden von Nullable-Typen)](using-nullable-types.md)  
- <xref:System.Nullable.GetUnderlyingType%2A>  
