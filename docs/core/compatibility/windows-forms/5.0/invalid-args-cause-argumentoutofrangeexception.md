---
title: 'Breaking Change: WinForms-Eigenschaften lösen nun ArgumentOutOfRangeException aus'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, bei dem einige Windows Forms-Eigenschaften bei ungültigen Argumenten nun ArgumentOutOfRangeException auslösen.
ms.date: 06/18/2020
ms.openlocfilehash: 94593047d16304ce401b23993ad4ca173c10812b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759499"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="6e0f7-103">WinForms-Eigenschaften lösen nun ArgumentOutOfRangeException aus</span><span class="sxs-lookup"><span data-stu-id="6e0f7-103">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="6e0f7-104">Einige Windows Forms-Eigenschaften lösen nun eine <xref:System.ArgumentOutOfRangeException> für ungültige Argumente aus, was zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-104">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="6e0f7-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6e0f7-105">Change description</span></span>

<span data-ttu-id="6e0f7-106">Zuvor haben diese Eigenschaften verschiedene Ausnahmen ausgelöst, wie z. B. <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException> oder <xref:System.ArgumentException>, wenn Argumente außerhalb des zulässigen Bereichs übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-106">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="6e0f7-107">Ab .NET 5.0 lösen diese Eigenschaften stattdessen eine <xref:System.ArgumentOutOfRangeException> aus, wenn Argumente außerhalb des zulässigen Bereichs übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-107">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="6e0f7-108">Das Auslösen einer <xref:System.ArgumentOutOfRangeException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-108">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="6e0f7-109">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6e0f7-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6e0f7-110">Version introduced</span></span>

<span data-ttu-id="6e0f7-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6e0f7-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6e0f7-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="6e0f7-112">Recommended action</span></span>

- <span data-ttu-id="6e0f7-113">Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="6e0f7-114">Behandeln Sie ggf. eine <xref:System.ArgumentOutOfRangeException>, wenn Sie die Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-114">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6e0f7-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6e0f7-115">Affected APIs</span></span>

<span data-ttu-id="6e0f7-116">In der folgenden Tabelle sind die betroffenen Eigenschaften und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="6e0f7-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="6e0f7-117">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6e0f7-117">Property</span></span> | <span data-ttu-id="6e0f7-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="6e0f7-118">Parameter name</span></span> | <span data-ttu-id="6e0f7-119">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="6e0f7-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="6e0f7-120">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="6e0f7-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="6e0f7-121">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="6e0f7-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="6e0f7-122">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="6e0f7-122">5.0 Preview 6</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
