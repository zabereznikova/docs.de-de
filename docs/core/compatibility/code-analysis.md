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
# <a name="code-analysis-breaking-changes"></a>Breaking Changes der Codeanalyse

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [CA1831: Verwenden Sie anstelle von Range-basierten Indexern "AsSpan" oder "AsMemory".](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | 5.0 |
| [CA2014: Verwenden Sie stackalloc nicht in Schleifen.](#ca2014-do-not-use-stackalloc-in-loops) | 5.0 |
| [CA2015: Keine Finalizer für von MemoryManager\<T> abgeleitete Typen definieren.](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | 5.0 |
| [CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value (Das Argument für den Konstruktor TaskCompletionSource muss ein TaskCreationOptions-Wert sein.)](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
