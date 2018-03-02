---
title: "Durchführen kulturunabhängiger Zeichenfolgenvergleiche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.CompareTo method
- String.Compare method
- string comparison [.NET Framework], culture-insensitive
- strings [.NET Framework], comparing
- culture-insensitive string operations, comparisons
- culture parameter
ms.assetid: abae50ef-32f7-4a50-a540-fd256fd1aed0
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fa689a685a58868ccd34b8bcbc4a779b9f826473
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-comparisons"></a><span data-ttu-id="4a047-102">Durchführen kulturunabhängiger Zeichenfolgenvergleiche</span><span class="sxs-lookup"><span data-stu-id="4a047-102">Performing Culture-Insensitive String Comparisons</span></span>
<span data-ttu-id="4a047-103">In der Standardeinstellung führt die <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methode kulturabhängige Vergleiche sowie Vergleiche unter Berücksichtigung der Groß-/Kleinschreibung aus.</span><span class="sxs-lookup"><span data-stu-id="4a047-103">By default, the <xref:System.String.Compare%2A?displayProperty=nameWithType> method performs culture-sensitive and case-sensitive comparisons.</span></span> <span data-ttu-id="4a047-104">Diese Methode schließt auch mehrere Überladungen ein, die einen `culture`-Parameter zur Angabe der zu verwendenden Kultur und einen `comparisonType`-Parameter zur Angabe der zu verwendenden Vergleichsregeln bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4a047-104">This method also includes several overloads that provide a `culture` parameter that lets you specify the culture to use, and a `comparisonType` parameter that lets you specify the comparison rules to use.</span></span> <span data-ttu-id="4a047-105">Durch den Aufruf dieser Methoden statt der Standardüberladung wird jede Mehrdeutigkeit hinsichtlich der in einem bestimmten Methodenaufruf verwendeten Regeln vermieden. Es wird verdeutlicht, ob ein bestimmter Vergleich kulturabhängig oder kulturunabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="4a047-105">Calling these methods instead of the default overload removes any ambiguity about the rules used in a particular method call, and makes it clear whether a particular comparison is culture-sensitive or culture-insensitive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a047-106">Beide Überladungen der <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode führen kulturabhängige Vergleiche durch, bei denen die Groß- und Kleinschreibung berücksichtigt wird. Sie können kulturunabhängige Vergleiche nicht mithilfe dieser Methode ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a047-106">Both overloads of the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method perform culture-sensitive and case-sensitive comparisons; you cannot use this method to perform culture-insensitive comparisons.</span></span> <span data-ttu-id="4a047-107">Aus Gründen der Übersichtlichkeit des Codes wird empfohlen, stattdessen die <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a047-107">For code clarity, we recommend that you use the <xref:System.String.Compare%2A?displayProperty=nameWithType> method instead.</span></span>  
  
 <span data-ttu-id="4a047-108">Geben Sie für kulturabhängige Vorgänge den <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>-Enumerationswert oder den <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>-Enumerationswert als `comparisonType`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="4a047-108">For culture-sensitive operations, specify the <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> or <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> enumeration value as the `comparisonType` parameter.</span></span> <span data-ttu-id="4a047-109">Wenn Sie einen kulturabhängigen Vergleich mithilfe einer anderen festgelegten Kultur als der aktuellen Kultur ausführen möchten, geben Sie das <xref:System.Globalization.CultureInfo>-Objekt an, das diese Kultur als `culture`-Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="4a047-109">If you want to perform a culture-sensitive comparison using a designated culture other than the current culture, specify the <xref:System.Globalization.CultureInfo> object that represents that culture as the `culture` parameter.</span></span>  
  
 <span data-ttu-id="4a047-110">Die kulturunabhängigen von der <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methode unterstützten Zeichenfolgenvergleiche sind entweder linguistisch (auf Grundlage der Sortierkonventionen der invarianten Kultur) oder nicht linguistisch (auf Grundlage des Ordnungswerts der Zeichen in der Zeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="4a047-110">The culture-insensitive string comparisons supported by the <xref:System.String.Compare%2A?displayProperty=nameWithType> method are either linguistic (based on the sorting conventions of the invariant culture) or non-linguistic (based on the ordinal value of the characters in the string).</span></span> <span data-ttu-id="4a047-111">Die meisten kulturunabhängigen Zeichenfolgenvergleiche sind nicht linguistisch.</span><span class="sxs-lookup"><span data-stu-id="4a047-111">Most culture-insensitive string comparisons are non-linguistic.</span></span> <span data-ttu-id="4a047-112">Geben Sie den <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>-Enumerationswert oder den <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType>-Enumerationswert als `comparisonType`-Parameter für diese Vergleiche an.</span><span class="sxs-lookup"><span data-stu-id="4a047-112">For these comparisons, specify the <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> or <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> enumeration value as the `comparisonType` parameter.</span></span> <span data-ttu-id="4a047-113">Wenn beispielsweise eine Sicherheitsentscheidung (z. B. ein Benutzername oder ein Kennwortvergleich) auf dem Ergebnis eines Zeichenfolgenvergleichs basiert, sollte der Vorgang kulturunabhängig und nicht linguistisch sein, um sicherzustellen, dass das Ergebnis nicht von den Konventionen einer bestimmten Kultur oder Sprache beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="4a047-113">For example, if a security decision (such as a user name or password comparison) is based on the result of a string comparison, the operation should be culture-insensitive and non-linguistic to ensure that the result is not affected by the conventions of a particular culture or language.</span></span>  
  
 <span data-ttu-id="4a047-114">Verwenden Sie einen kulturunabhängigen linguistischen Zeichenfolgenvergleich, wenn Sie linguistisch relevante Zeichenfolgen mehrerer Kulturen auf eine konsistente Weise behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="4a047-114">Use culture-insensitive linguistic string comparison if you want to handle linguistically relevant strings from multiple cultures in a consistent way.</span></span> <span data-ttu-id="4a047-115">Wenn die Anwendung z. B. Wörter anzeigt, die mehrere Zeichensätze in einem Listenfeld verwenden, können Sie Wörter in der gleichen Reihenfolge unabhängig von der aktuellen Kultur anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4a047-115">For example, if your application displays words that use multiple character sets in a list box, you might want to display words in the same order regardless of the current culture.</span></span> <span data-ttu-id="4a047-116">Für kulturunabhängige linguistische Vergleiche definiert .NET Framework eine invariante Kultur, die auf den linguistischen Konventionen der englischen Sprache basiert.</span><span class="sxs-lookup"><span data-stu-id="4a047-116">For culture-insensitive linguistic comparisons, the .NET Framework defines an invariant culture that is based on the linguistic conventions of English.</span></span> <span data-ttu-id="4a047-117">Geben Sie <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> oder <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> als `comparisonType`-Parameter an, um einen kulturunabhängigen linguistischen Vergleich auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4a047-117">To perform a culture-insensitive linguistic comparison, specify <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> or <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> as the `comparisonType` parameter.</span></span>  
  
 <span data-ttu-id="4a047-118">Im folgenden Beispiel werden zwei kulturunabhängige, nicht linguistische Zeichenfolgenvergleiche ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4a047-118">The following example performs two culture-insensitive, non-linguistic string comparisons.</span></span> <span data-ttu-id="4a047-119">Beim ersten Beispiel wird die Groß-/Kleinschreibung beachtet, beim zweiten nicht.</span><span class="sxs-lookup"><span data-stu-id="4a047-119">The first is case-sensitive, but the second is not.</span></span>  
  
 [!code-csharp[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/cs/cultureinsensitive1.cs#1)]
 [!code-vb[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/vb/cultureinsensitive1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4a047-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a047-120">See Also</span></span>  
 <xref:System.String.Compare%2A?displayProperty=nameWithType>  
 <xref:System.String.CompareTo%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4a047-121">Durchführen kulturunabhängiger Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="4a047-121">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)  
 [<span data-ttu-id="4a047-122">Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4a047-122">Best Practices for Using Strings</span></span>](../../../docs/standard/base-types/best-practices-strings.md)
