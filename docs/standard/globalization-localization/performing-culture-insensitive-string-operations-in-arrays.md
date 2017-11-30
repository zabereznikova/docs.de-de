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
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="6dab9-102">Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays</span><span class="sxs-lookup"><span data-stu-id="6dab9-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="6dab9-103">Überladungen der der <xref:System.Array.Sort%2A?displayProperty=nameWithType> und <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> Methoden führen kulturabhängigen Sortierungen standardmäßig mit der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6dab9-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6dab9-104">Kulturabhängige-Ergebnisse, die von diesen Methoden zurückgegebenen können je nach Kultur aufgrund von Unterschieden bei Sortierreihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="6dab9-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="6dab9-105">Um kulturabhängige Verhalten zu vermeiden, verwenden Sie eine der Überladungen dieser Methode, die akzeptiert eine `comparer` Parameter.</span><span class="sxs-lookup"><span data-stu-id="6dab9-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="6dab9-106">Die `comparer` Parameter gibt die <xref:System.Collections.IComparer> Implementierung, die beim Vergleichen von Elementen im Array.</span><span class="sxs-lookup"><span data-stu-id="6dab9-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="6dab9-107">Geben Sie eine benutzerdefinierte, invariante Comparer-Klasse, verwendet für den Parameter <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6dab9-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6dab9-108">Ein Beispiel einer benutzerdefinierten invariante Comparer-Klasse finden Sie unter "Verwenden der SortedList-Klasse" des Themas die [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="6dab9-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="6dab9-109">**Hinweis** übergeben **CultureInfo.InvariantCulture** Methode führt zu einem Vergleich einen kulturunabhängigen Vergleich.</span><span class="sxs-lookup"><span data-stu-id="6dab9-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="6dab9-110">Dies bewirkt jedoch keinen nicht linguistischen Vergleich, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="6dab9-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="6dab9-111">Und dadurch werden auch keine Sicherheitsentscheidungen anhand des Vergleichsergebnisses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6dab9-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="6dab9-112">Für einen nicht linguistischen Vergleich oder Unterstützung für Ergebnis basierende sicherheitsentscheidungen, die Anwendung sollte eine Vergleichsmethode, die akzeptiert verwenden eine <xref:System.StringComparison> Wert.</span><span class="sxs-lookup"><span data-stu-id="6dab9-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="6dab9-113">Leitet die Anwendung sollte <xref:System.StringComparison.Ordinal>.</span><span class="sxs-lookup"><span data-stu-id="6dab9-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dab9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dab9-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="6dab9-115">Durchführen kulturunabhängiger Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="6dab9-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
