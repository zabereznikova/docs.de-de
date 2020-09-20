---
title: Breaking Changes der Codeanalyse
description: In diesem Artikel werden die Breaking Changes an .NET-Quellcodeanalyse-Tools aufgeführt.
ms.date: 09/02/2020
ms.openlocfilehash: 20badd69b316e1d87700b3c5061a71d648b71c64
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065162"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="3ccda-103">Breaking Changes der Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="3ccda-103">Code analysis breaking changes</span></span>

<span data-ttu-id="3ccda-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="3ccda-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="3ccda-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="3ccda-105">Breaking change</span></span> | <span data-ttu-id="3ccda-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3ccda-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="3ccda-107">CA1416: Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="3ccda-107">CA1416: Platform compatibility</span></span>](#ca1416-platform-compatibility) | <span data-ttu-id="3ccda-108">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-108">5.0</span></span> |
| [<span data-ttu-id="3ccda-109">CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke</span><span class="sxs-lookup"><span data-stu-id="3ccda-109">CA1417: OutAttribute on string parameter for P/Invoke</span></span>](#ca1417-outattribute-on-string-parameter-for-pinvoke) | <span data-ttu-id="3ccda-110">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-110">5.0</span></span> |
| [<span data-ttu-id="3ccda-111">CA1831: Anstelle von bereichsbasierten Indexern AsSpan für Zeichenfolgen verwenden</span><span class="sxs-lookup"><span data-stu-id="3ccda-111">CA1831: Use AsSpan instead of Range-based indexers for string</span></span>](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | <span data-ttu-id="3ccda-112">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-112">5.0</span></span> |
| [<span data-ttu-id="3ccda-113">CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="3ccda-113">CA2013: Do not use ReferenceEquals with value types</span></span>](#ca2013-do-not-use-referenceequals-with-value-types) | <span data-ttu-id="3ccda-114">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-114">5.0</span></span> |
| [<span data-ttu-id="3ccda-115">CA2014: Verwenden Sie stackalloc nicht in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="3ccda-115">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="3ccda-116">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-116">5.0</span></span> |
| [<span data-ttu-id="3ccda-117">CA2015: Keine Finalizer für von MemoryManager\<T> abgeleitete Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="3ccda-117">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="3ccda-118">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-118">5.0</span></span> |
| [<span data-ttu-id="3ccda-119">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value (Das Argument für den Konstruktor TaskCompletionSource muss ein TaskCreationOptions-Wert sein.)</span><span class="sxs-lookup"><span data-stu-id="3ccda-119">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="3ccda-120">5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-120">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="3ccda-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3ccda-121">.NET 5.0</span></span>

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
