---
title: Durchführen kulturunabhängiger Zeichenfolgenoperationen
ms.date: 08/22/2018
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 868f36a1025f0b121a8765edf50bb42679736240
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829764"
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="0145f-102">Durchführen kulturunabhängiger Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="0145f-102">Performing culture-insensitive string operations</span></span>

<span data-ttu-id="0145f-103">Die meisten .NET-Methoden, die standardmäßig kulturabhängige Zeichenfolgenoperationen durchführen, stellen Methodenüberladungen bereit, für die Sie die zu verwendende Kultur explizit angeben können, indem Sie einen <xref:System.Globalization.CultureInfo>-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="0145f-103">Most .NET methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="0145f-104">Diese Überladungen ermöglichen es Ihnen, kulturelle Variationen in Groß-/Kleinschreibungszuordnungen und Sortierregeln zu eliminieren und kulturunabhängige Ergebnisse zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="0145f-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="0145f-105">Dieser Abschnitt enthält die folgenden Artikel, in denen erläutert wird, wie kulturunabhängige Zeichenfolgenoperationen mit .NET-Methoden durchgeführt werden, die standardmäßig kulturabhängig sind.</span><span class="sxs-lookup"><span data-stu-id="0145f-105">This section provides the following articles to demonstrate how to perform culture-insensitive string operations using .NET methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0145f-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0145f-106">In this section</span></span>  
 [<span data-ttu-id="0145f-107">Durchführen kulturunabhängiger Zeichenfolgenvergleiche</span><span class="sxs-lookup"><span data-stu-id="0145f-107">Performing Culture-Insensitive String Comparisons</span></span>](performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="0145f-108">Beschreibt die Verwendung der <xref:System.String.Compare%2A?displayProperty=nameWithType>- und <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Zeichenfolgenvergleiche.</span><span class="sxs-lookup"><span data-stu-id="0145f-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="0145f-109">Durchführen kulturunabhängiger Schreibungsänderungen</span><span class="sxs-lookup"><span data-stu-id="0145f-109">Performing Culture-Insensitive Case Changes</span></span>](performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="0145f-110">Beschreibt die Verwendung der <xref:System.String.ToUpper%2A?displayProperty=nameWithType>-, <xref:System.String.ToLower%2A?displayProperty=nameWithType>-, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>- und <xref:System.Char.ToLower%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Schreibungsänderungen.</span><span class="sxs-lookup"><span data-stu-id="0145f-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="0145f-111">Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen</span><span class="sxs-lookup"><span data-stu-id="0145f-111">Performing Culture-Insensitive String Operations in Collections</span></span>](performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="0145f-112">Beschreibt die Verwendung von <xref:System.Collections.CaseInsensitiveComparer>- und <xref:System.Collections.CaseInsensitiveHashCodeProvider>-Klasse, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> und <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> für kulturunabhängige Operationen in Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="0145f-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="0145f-113">Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays</span><span class="sxs-lookup"><span data-stu-id="0145f-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="0145f-114">Beschreibt die Verwendung von <xref:System.Array.Sort%2A?displayProperty=nameWithType>- und <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>-Methode für kulturunabhängige Operationen in Arrays.</span><span class="sxs-lookup"><span data-stu-id="0145f-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0145f-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0145f-115">Related sections</span></span>  
 [<span data-ttu-id="0145f-116">Kulturunabhängige Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="0145f-116">Culture-Insensitive String Operations</span></span>](culture-insensitive-string-operations.md)  
 <span data-ttu-id="0145f-117">Beschreibt, warum Sie die Kultur berücksichtigen sollten, wenn Sie Operationen mit Zeichenfolgen ausführen, und enthält Richtlinien dazu, wann kulturabhängige Operationen und wann kulturunabhängige Operationen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="0145f-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="0145f-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0145f-118">See also</span></span>

- [<span data-ttu-id="0145f-119">Sortiergewichtungstabellen (für .NET auf Windows-Systemen)</span><span class="sxs-lookup"><span data-stu-id="0145f-119">Sorting Weight Tables (for .NET on Windows systems)</span></span>](https://www.microsoft.com/download/details.aspx?id=10921)
- [<span data-ttu-id="0145f-120">Default Unicode Collation Element Table (für .NET Core unter Linux und macOS)</span><span class="sxs-lookup"><span data-stu-id="0145f-120">Default Unicode Collation Element Table (for .NET Core on Linux and macOS)</span></span>](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
