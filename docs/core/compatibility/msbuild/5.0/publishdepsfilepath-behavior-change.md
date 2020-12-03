---
title: 'Breaking Change: Behavior Change von PublishDepsFilePath'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den die MSBuild-Eigenschaft „PublishDepsFilePath“ bei Einzeldateianwendungen leer ist.
ms.date: 09/17/2020
ms.openlocfilehash: 70631beff31aa3388e59f3b79875ef437351451a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759570"
---
# <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="292df-103">Behavior Change von PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="292df-103">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="292df-104">Die MSBuild-Eigenschaft `PublishDepsFilePath` ist für Anwendungen mit nur einer Datei leer.</span><span class="sxs-lookup"><span data-stu-id="292df-104">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="292df-105">Zusätzlich darf bei Anwendungen, die nicht nur aus einer einzelnen Datei bestehen, die Datei *deps.json* erst später im Build in das Ausgabeverzeichnis kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="292df-105">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="292df-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="292df-106">Version introduced</span></span>

<span data-ttu-id="292df-107">5.0</span><span class="sxs-lookup"><span data-stu-id="292df-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="292df-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="292df-108">Change description</span></span>

<span data-ttu-id="292df-109">In früheren .NET-Versionen ist die MSBuild-Eigenschaft `PublishDepsFilePath` der Pfad zur Datei *deps.json* der App im Ausgabeverzeichnis für Anwendungen, die nicht nur aus einer Datei bestehen, und ein Pfad im Zwischenverzeichnis für Anwendungen mit nur einer Datei.</span><span class="sxs-lookup"><span data-stu-id="292df-109">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="292df-110">Ab .NET 5.0 ist `PublishDepsFilePath` bei Anwendungen mit nur einer Datei leer. Die neue Eigenschaft `IntermediateDepsFilePath` gibt den Speicherort von *deps.json* im Zwischenverzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="292df-110">Starting in .NET 5.0, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="292df-111">Zusätzlich darf bei Anwendungen, die nicht nur aus einer einzelnen Datei bestehen, die Datei *deps.json* erst später im Build in das Ausgabeverzeichnis (d. h. den von `PublishDepsFilePath` angegebenen Pfad) kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="292df-111">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="292df-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="292df-112">Reason for change</span></span>

<span data-ttu-id="292df-113">Diese Änderung ist aus mehreren Gründen erfolgt:</span><span class="sxs-lookup"><span data-stu-id="292df-113">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="292df-114">Aufgrund eines Refactorings der Veröffentlichungslogik zur Unterstützung [verbesserter Apps mit nur einer Datei](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="292df-114">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="292df-115">Um sich bei Apps mit nur einer Datei vor Zielen zu schützen, die versuchen, die Datei *deps.json* neu zu schreiben, nachdem die Datei *deps.json* bereits gebündelt wurde, sodass die Anwendung nicht unbemerkt beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="292df-115">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="292df-116">Aus diesem Grund ist `PublishDepsFilePath` für Anwendungen mit nur einer Datei leer.</span><span class="sxs-lookup"><span data-stu-id="292df-116">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="292df-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="292df-117">Recommended action</span></span>

<span data-ttu-id="292df-118">Ziele, die die Datei *deps.json* neu schreiben, sollten dies im Allgemeinen mit der Eigenschaft `IntermediateDepsFilePath` tun.</span><span class="sxs-lookup"><span data-stu-id="292df-118">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="292df-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="292df-119">Affected APIs</span></span>

<span data-ttu-id="292df-120">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="292df-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
