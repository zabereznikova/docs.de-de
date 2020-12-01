---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031993"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a><span data-ttu-id="77080-101">Verarbeiten von Corrupted State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="77080-101">Handling corrupted state exceptions is not supported</span></span>

<span data-ttu-id="77080-102">Das Verarbeiten von Corrupted State Exceptions wird in .NET Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77080-102">Handling corrupted-process-state exceptions in .NET Core is not supported.</span></span>

#### <a name="change-description"></a><span data-ttu-id="77080-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="77080-103">Change description</span></span>

<span data-ttu-id="77080-104">Zuvor konnten Corrupted State Exceptions durch Ausnahmehandler mit verwaltetem Code abgefangen und verarbeitet werden, indem z. B. eine [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md)-Anweisung in C# verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="77080-104">Previously, corrupted-process-state exceptions could be caught and handled by managed code exception handlers, for example, by using a [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) statement in C#.</span></span>

<span data-ttu-id="77080-105">Ab .NET Core 1.0 können Corrupted State Exceptions nicht mehr von verwaltetem Code verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="77080-105">Starting in .NET Core 1.0, corrupted-process-state exceptions cannot be handled by managed code.</span></span> <span data-ttu-id="77080-106">Die Common Language Runtime liefert keine Corrupted State Exceptions an verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="77080-106">The common language runtime doesn't deliver corrupted-process-state exceptions to managed code.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77080-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="77080-107">Version introduced</span></span>

<span data-ttu-id="77080-108">1.0</span><span class="sxs-lookup"><span data-stu-id="77080-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77080-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="77080-109">Recommended action</span></span>

<span data-ttu-id="77080-110">Vermeiden Sie die Notwendigkeit einer Verarbeitung von Corrupted State Exceptions, indem Sie sich mit den Situationen befassen, die zu diesen geführt haben.</span><span class="sxs-lookup"><span data-stu-id="77080-110">Avoid the need to handle corrupted-process-state exceptions by addressing the situations that lead to them instead.</span></span> <span data-ttu-id="77080-111">Wenn es absolut notwendig ist, Corrupted State Exceptions zu verarbeiten, schreiben Sie den Ausnahmehandler in C- oder C++-Code.</span><span class="sxs-lookup"><span data-stu-id="77080-111">If it's absolutely necessary to handle corrupted-process-state exceptions, write the exception handler in C or C++ code.</span></span>

#### <a name="category"></a><span data-ttu-id="77080-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="77080-112">Category</span></span>

<span data-ttu-id="77080-113">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="77080-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77080-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="77080-114">Affected APIs</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [<span data-ttu-id="77080-115">legacyCorruptedStateExceptionsPolicy element</span><span class="sxs-lookup"><span data-stu-id="77080-115">legacyCorruptedStateExceptionsPolicy element</span></span>](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
