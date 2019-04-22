---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774323"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="ee013-101">List\<T>.ForEach kann beim Ändern eines Listenelements eine Ausnahme auslösen</span><span class="sxs-lookup"><span data-stu-id="ee013-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ee013-102">Details</span><span class="sxs-lookup"><span data-stu-id="ee013-102">Details</span></span>|<span data-ttu-id="ee013-103">Ab .NET Framework 4.5 löst ein <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})>-Enumerator eine <xref:System.InvalidOperationException?displayProperty=name>-Ausnahme aus, wenn ein Element in der aufrufenden Sammlung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ee013-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="ee013-104">Zuvor hätte dies keine Ausnahme ausgelöst, aber zu Racebedingungen geführt.</span><span class="sxs-lookup"><span data-stu-id="ee013-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="ee013-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ee013-105">Suggestion</span></span>|<span data-ttu-id="ee013-106">Im Idealfall sollte der Code unveränderlich sein, damit Listen nicht geändert werden, während ihre Elemente aufgezählt werden, da dies nie ein sicherer Vorgang ist.</span><span class="sxs-lookup"><span data-stu-id="ee013-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="ee013-107">Eine App kann auf .NET Framework 4.0 ausgelegt werden, um zum vorherigen Verhalten zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="ee013-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="ee013-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="ee013-108">Scope</span></span>|<span data-ttu-id="ee013-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ee013-109">Edge</span></span>|
|<span data-ttu-id="ee013-110">Version</span><span class="sxs-lookup"><span data-stu-id="ee013-110">Version</span></span>|<span data-ttu-id="ee013-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ee013-111">4.5</span></span>|
|<span data-ttu-id="ee013-112">Typ</span><span class="sxs-lookup"><span data-stu-id="ee013-112">Type</span></span>|<span data-ttu-id="ee013-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="ee013-113">Retargeting</span></span>|
|<span data-ttu-id="ee013-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ee013-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
