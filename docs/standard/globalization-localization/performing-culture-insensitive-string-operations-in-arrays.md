---
title: Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
ms.openlocfilehash: 051ee77ae5d6552e26e0216d58734d90188475f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120804"
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays

Überladungen der <xref:System.Array.Sort%2A?displayProperty=nameWithType>- und <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Methode führen kulturabhängige Sortierungen standardmäßig mit der <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>-Eigenschaft aus. Die kulturabhängigen Ergebnisse, die von diesen Methoden zurückgegeben werden, können aufgrund von Unterschieden bei Sortierreihenfolgen je nach Kultur variieren. Um kulturabhängiges Verhalten zu vermeiden, verwenden Sie eine der Überladungen dieser Methode, die einen `comparer`-Parameter akzeptiert. Der `comparer`-Parameter gibt die <xref:System.Collections.IComparer>-Implementierung an, die beim Vergleich von Elementen im Array zu verwenden ist. Geben Sie für den Parameter eine benutzerdefinierte invariante Comparer-Klasse an, in der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> verwendet wird. Ein Beispiel einer benutzerdefinierten invarianten Comparer-Klasse finden Sie im Unterthema „Verwenden der SortedList-Klasse“ des Themas [Durchführen kulturunabhängiger Zeichenfolgenvorgänge in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).

> [!NOTE]
> Wenn Sie **CultureInfo.InvariantCulture** einer Vergleichsmethode übergeben, wird ein kulturunabhängiger Vergleich ausgeführt. Dies bewirkt jedoch keinen nicht linguistischen Vergleich, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen. Und dadurch werden auch keine Sicherheitsentscheidungen anhand des Vergleichsergebnisses unterstützt. Für einen nicht linguistischen Vergleich oder Unterstützung für ergebnisbasierte Sicherheitsentscheidungen sollte die Anwendung eine Vergleichsmethode verwenden, die einen <xref:System.StringComparison>-Wert akzeptiert. Die Anwendung sollte dann <xref:System.StringComparison.Ordinal> übergeben.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>
- <xref:System.Collections.IComparer>
- [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
