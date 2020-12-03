---
title: 'Breaking Change: Mit DataGridView verbundene APIs lösen jetzt InvalidOperationException aus'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den einige APIs, die im Zusammenhang mit DataGridView stehen, eine Ausnahme auslösen, wenn der Wert „DataGridViewCellAccessibleObject.Owner“ des Objekts NULL ist.
ms.date: 09/18/2020
ms.openlocfilehash: 927b1c9160700159a45aa1472b8d96f1a9ecfe25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759511"
---
# <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="94225-103">Mit DataGridView verbundene APIs lösen jetzt InvalidOperationException aus</span><span class="sxs-lookup"><span data-stu-id="94225-103">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="94225-104">Einige mit <xref:System.Windows.Forms.DataGridView> verbundene APIs lösen jetzt eine <xref:System.InvalidOperationException>-Klasse aus, wenn der Wert der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType>-Eigenschaft `null` ist.</span><span class="sxs-lookup"><span data-stu-id="94225-104">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

## <a name="change-description"></a><span data-ttu-id="94225-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="94225-105">Change description</span></span>

<span data-ttu-id="94225-106">In früheren .NET-Versionen lösen die betroffenen APIs eine <xref:System.NullReferenceException>-Klasse aus, wenn sie aufgerufen werden und der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner>-Wert `null` ist.</span><span class="sxs-lookup"><span data-stu-id="94225-106">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="94225-107">Ab .NET 5.0 lösen diese APIs anstelle einer <xref:System.NullReferenceException>-Klasse eine <xref:System.InvalidOperationException>-Klasse aus, wenn der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner>-Wert beim Aufruf `null` ist.</span><span class="sxs-lookup"><span data-stu-id="94225-107">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="94225-108">Das Auslösen einer <xref:System.InvalidOperationException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="94225-108">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="94225-109">Außerdem wird die Debugfunktion verbessert, indem deutlich auf die ungültige Eigenschaft hingewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="94225-109">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="94225-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="94225-110">Version introduced</span></span>

<span data-ttu-id="94225-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="94225-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="94225-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="94225-112">Recommended action</span></span>

<span data-ttu-id="94225-113">Überprüfen Sie den Code, und aktualisieren Sie ihn bei Bedarf, um zu verhindern, dass die betroffenen Typen mit der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner>-Eigenschaft als `null` konstruiert werden.</span><span class="sxs-lookup"><span data-stu-id="94225-113">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="94225-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="94225-114">Affected APIs</span></span>

<span data-ttu-id="94225-115">In der folgenden Tabelle sind die betroffenen Eigenschaften und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="94225-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="94225-116">Betroffene Methode oder Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94225-116">Affected method or property</span></span> | <span data-ttu-id="94225-117">Überprüfte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94225-117">Validated property</span></span> | <span data-ttu-id="94225-118">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="94225-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-119">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-120">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-121">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-122">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-123">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-124">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-125">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-126">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-127">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-128">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-129">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="94225-130">5.0</span><span class="sxs-lookup"><span data-stu-id="94225-130">5.0</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State`
- `M:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)`
- `M:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction`

### Category

Windows Forms

-->
