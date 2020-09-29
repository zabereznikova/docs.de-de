---
ms.openlocfilehash: 077eadb05ab16f5cec8817b89bc771de0c94aefa
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679322"
---
### <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="3368f-101">Behavior Change von PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="3368f-101">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="3368f-102">Die MSBuild-Eigenschaft `PublishDepsFilePath` ist für Anwendungen mit nur einer Datei leer.</span><span class="sxs-lookup"><span data-stu-id="3368f-102">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="3368f-103">Zusätzlich darf bei Anwendungen, die nicht nur aus einer einzelnen Datei bestehen, die Datei *deps.json* erst später im Build in das Ausgabeverzeichnis kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="3368f-103">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3368f-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3368f-104">Version introduced</span></span>

<span data-ttu-id="3368f-105">5.0</span><span class="sxs-lookup"><span data-stu-id="3368f-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="3368f-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3368f-106">Change description</span></span>

<span data-ttu-id="3368f-107">In früheren .NET-Versionen ist die MSBuild-Eigenschaft `PublishDepsFilePath` der Pfad zur Datei *deps.json* der App im Ausgabeverzeichnis für Anwendungen, die nicht nur aus einer Datei bestehen, und ein Pfad im Zwischenverzeichnis für Anwendungen mit nur einer Datei.</span><span class="sxs-lookup"><span data-stu-id="3368f-107">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="3368f-108">Ab .NET 5.0 ist `PublishDepsFilePath` bei Anwendungen mit nur einer Datei leer. Die neue Eigenschaft `IntermediateDepsFilePath` gibt den Speicherort von *deps.json* im Zwischenverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="3368f-108">Starting in .NET 5.0, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="3368f-109">Zusätzlich darf bei Anwendungen, die nicht nur aus einer einzelnen Datei bestehen, die Datei *deps.json* erst später im Build in das Ausgabeverzeichnis (d. h. den von `PublishDepsFilePath` angegebenen Pfad) kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="3368f-109">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3368f-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3368f-110">Reason for change</span></span>

<span data-ttu-id="3368f-111">Diese Änderung ist aus mehreren Gründen erfolgt:</span><span class="sxs-lookup"><span data-stu-id="3368f-111">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="3368f-112">Aufgrund eines Refactorings der Veröffentlichungslogik zur Unterstützung [verbesserter Apps mit nur einer Datei](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="3368f-112">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="3368f-113">Um sich bei Apps mit nur einer Datei vor Zielen zu schützen, die versuchen, die Datei *deps.json* neu zu schreiben, nachdem die Datei *deps.json* bereits gebündelt wurde, sodass die Anwendung nicht unbemerkt beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="3368f-113">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="3368f-114">Aus diesem Grund ist `PublishDepsFilePath` für Anwendungen mit nur einer Datei leer.</span><span class="sxs-lookup"><span data-stu-id="3368f-114">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3368f-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="3368f-115">Recommended action</span></span>

<span data-ttu-id="3368f-116">Ziele, die die Datei *deps.json* neu schreiben, sollten dies im Allgemeinen mit der Eigenschaft `IntermediateDepsFilePath` tun.</span><span class="sxs-lookup"><span data-stu-id="3368f-116">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

#### <a name="category"></a><span data-ttu-id="3368f-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3368f-117">Category</span></span>

<span data-ttu-id="3368f-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="3368f-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3368f-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3368f-119">Affected APIs</span></span>

<span data-ttu-id="3368f-120">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3368f-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
