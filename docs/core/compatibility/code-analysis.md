---
title: Breaking Changes der Codeanalyse
description: In diesem Artikel werden die Breaking Changes an .NET-Quellcodeanalyse-Tools aufgeführt.
ms.date: 09/02/2020
ms.openlocfilehash: 3cbe2ecf5d08084db542db0c2da016f1f391452e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538921"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="edcf9-103">Breaking Changes der Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="edcf9-103">Code analysis breaking changes</span></span>

<span data-ttu-id="edcf9-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="edcf9-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="edcf9-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="edcf9-105">Breaking change</span></span> | <span data-ttu-id="edcf9-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="edcf9-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="edcf9-107">CA1416: Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="edcf9-107">CA1416: Platform compatibility</span></span>](#ca1416-platform-compatibility) | <span data-ttu-id="edcf9-108">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-108">5.0</span></span> |
| [<span data-ttu-id="edcf9-109">CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke</span><span class="sxs-lookup"><span data-stu-id="edcf9-109">CA1417: OutAttribute on string parameter for P/Invoke</span></span>](#ca1417-outattribute-on-string-parameter-for-pinvoke) | <span data-ttu-id="edcf9-110">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-110">5.0</span></span> |
| [<span data-ttu-id="edcf9-111">CA1831: Anstelle von bereichsbasierten Indexern AsSpan für Zeichenfolgen verwenden</span><span class="sxs-lookup"><span data-stu-id="edcf9-111">CA1831: Use AsSpan instead of Range-based indexers for string</span></span>](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | <span data-ttu-id="edcf9-112">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-112">5.0</span></span> |
| [<span data-ttu-id="edcf9-113">CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.</span><span class="sxs-lookup"><span data-stu-id="edcf9-113">CA2013: Do not use ReferenceEquals with value types</span></span>](#ca2013-do-not-use-referenceequals-with-value-types) | <span data-ttu-id="edcf9-114">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-114">5.0</span></span> |
| [<span data-ttu-id="edcf9-115">CA2014: Verwenden Sie stackalloc nicht in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="edcf9-115">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="edcf9-116">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-116">5.0</span></span> |
| [<span data-ttu-id="edcf9-117">CA2015: Keine Finalizer für von MemoryManager\<T> abgeleitete Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="edcf9-117">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="edcf9-118">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-118">5.0</span></span> |
| [<span data-ttu-id="edcf9-119">CA2200: Erneut ausführen, um Stapeldetails beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="edcf9-119">CA2200: Rethrow to preserve stack details</span></span>](#ca2200-rethrow-to-preserve-stack-details) | <span data-ttu-id="edcf9-120">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-120">5.0</span></span> |
| [<span data-ttu-id="edcf9-121">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value (Das Argument für den Konstruktor TaskCompletionSource muss ein TaskCreationOptions-Wert sein.)</span><span class="sxs-lookup"><span data-stu-id="edcf9-121">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="edcf9-122">5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-122">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="edcf9-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="edcf9-123">.NET 5.0</span></span>

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

[!INCLUDE [ca2200-rethrow-to-preserve-stack-details](../../../includes/core-changes/codeanalysis/5.0/ca2200-rethrow-to-preserve-stack-details.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
