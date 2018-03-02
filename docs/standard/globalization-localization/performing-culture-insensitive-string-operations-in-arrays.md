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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d273fbaa792092f5ea56bfa59392794b6728ed67
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="c06e0-102">Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays</span><span class="sxs-lookup"><span data-stu-id="c06e0-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="c06e0-103">Überladungen der <xref:System.Array.Sort%2A?displayProperty=nameWithType>- und <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Methode führen kulturabhängige Sortierungen standardmäßig mit der <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>-Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="c06e0-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c06e0-104">Die kulturabhängigen Ergebnisse, die von diesen Methoden zurückgegeben werden, können aufgrund von Unterschieden bei Sortierreihenfolgen je nach Kultur variieren.</span><span class="sxs-lookup"><span data-stu-id="c06e0-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="c06e0-105">Um kulturabhängiges Verhalten zu vermeiden, verwenden Sie eine der Überladungen dieser Methode, die einen `comparer`-Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c06e0-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="c06e0-106">Der `comparer`-Parameter gibt die <xref:System.Collections.IComparer>-Implementierung an, die beim Vergleich von Elementen im Array zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="c06e0-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="c06e0-107">Geben Sie für den Parameter eine benutzerdefinierte invariante Comparer-Klasse an, in der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c06e0-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c06e0-108">Ein Beispiel einer benutzerdefinierten invarianten Comparer-Klasse finden Sie im Unterthema „Verwenden der SortedList-Klasse“ des Themas [Durchführen kulturunabhängiger Zeichenfolgenvorgänge in Auflistungen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="c06e0-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="c06e0-109">**Hinweis** Wenn Sie **CultureInfo.InvariantCulture** an eine Vergleichsmethode übergeben, wird ein kulturunabhängiger Vergleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c06e0-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="c06e0-110">Dies bewirkt jedoch keinen nicht linguistischen Vergleich, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="c06e0-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="c06e0-111">Und dadurch werden auch keine Sicherheitsentscheidungen anhand des Vergleichsergebnisses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c06e0-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="c06e0-112">Für einen nicht linguistischen Vergleich oder Unterstützung für ergebnisbasierte Sicherheitsentscheidungen sollte die Anwendung eine Vergleichsmethode verwenden, die einen <xref:System.StringComparison>-Wert akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c06e0-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="c06e0-113">Die Anwendung sollte dann <xref:System.StringComparison.Ordinal> übergeben.</span><span class="sxs-lookup"><span data-stu-id="c06e0-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06e0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c06e0-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="c06e0-115">Durchführen kulturunabhängiger Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="c06e0-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
