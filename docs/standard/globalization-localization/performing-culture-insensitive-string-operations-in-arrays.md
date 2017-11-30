---
title: "Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays
Überladungen der der <xref:System.Array.Sort%2A?displayProperty=nameWithType> und <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> Methoden führen kulturabhängigen Sortierungen standardmäßig mit der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> Eigenschaft. Kulturabhängige-Ergebnisse, die von diesen Methoden zurückgegebenen können je nach Kultur aufgrund von Unterschieden bei Sortierreihenfolgen. Um kulturabhängige Verhalten zu vermeiden, verwenden Sie eine der Überladungen dieser Methode, die akzeptiert eine `comparer` Parameter. Die `comparer` Parameter gibt die <xref:System.Collections.IComparer> Implementierung, die beim Vergleichen von Elementen im Array. Geben Sie eine benutzerdefinierte, invariante Comparer-Klasse, verwendet für den Parameter <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Ein Beispiel einer benutzerdefinierten invariante Comparer-Klasse finden Sie unter "Verwenden der SortedList-Klasse" des Themas die [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) Thema.  
  
 **Hinweis** übergeben **CultureInfo.InvariantCulture** Methode führt zu einem Vergleich einen kulturunabhängigen Vergleich. Dies bewirkt jedoch keinen nicht linguistischen Vergleich, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen. Und dadurch werden auch keine Sicherheitsentscheidungen anhand des Vergleichsergebnisses unterstützt. Für einen nicht linguistischen Vergleich oder Unterstützung für Ergebnis basierende sicherheitsentscheidungen, die Anwendung sollte eine Vergleichsmethode, die akzeptiert verwenden eine <xref:System.StringComparison> Wert. Leitet die Anwendung sollte <xref:System.StringComparison.Ordinal>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
