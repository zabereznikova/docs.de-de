---
title: Breaking Changes der Codeanalyse
description: In diesem Artikel werden die Breaking Changes an .NET-Quellcodeanalyse-Tools aufgeführt.
ms.date: 08/22/2020
ms.openlocfilehash: 8b2b50c5f03a3ca971aefd0f2cf53624dfa82274
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465573"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="e1506-103">Breaking Changes der Codeanalyse</span><span class="sxs-lookup"><span data-stu-id="e1506-103">Code analysis breaking changes</span></span>

<span data-ttu-id="e1506-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="e1506-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e1506-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="e1506-105">Breaking change</span></span> | <span data-ttu-id="e1506-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e1506-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="e1506-107">CA1831: Verwenden Sie anstelle von Range-basierten Indexern "AsSpan" oder "AsMemory".</span><span class="sxs-lookup"><span data-stu-id="e1506-107">CA1831: Use AsSpan or AsMemory instead of Range-based indexer</span></span>](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | <span data-ttu-id="e1506-108">5.0</span><span class="sxs-lookup"><span data-stu-id="e1506-108">5.0</span></span> |
| [<span data-ttu-id="e1506-109">CA2014: Verwenden Sie stackalloc nicht in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="e1506-109">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="e1506-110">5.0</span><span class="sxs-lookup"><span data-stu-id="e1506-110">5.0</span></span> |
| [<span data-ttu-id="e1506-111">CA2015: Keine Finalizer für von MemoryManager\<T> abgeleitete Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="e1506-111">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="e1506-112">5.0</span><span class="sxs-lookup"><span data-stu-id="e1506-112">5.0</span></span> |
| [<span data-ttu-id="e1506-113">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value (Das Argument für den Konstruktor TaskCompletionSource muss ein TaskCreationOptions-Wert sein.)</span><span class="sxs-lookup"><span data-stu-id="e1506-113">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="e1506-114">5.0</span><span class="sxs-lookup"><span data-stu-id="e1506-114">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="e1506-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e1506-115">.NET 5.0</span></span>

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
