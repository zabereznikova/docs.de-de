---
ms.openlocfilehash: b6cb7c4b479551ff4563998f310ff518d935f48a
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656338"
---
### <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="255ab-101">Mit DataGridView verbundene APIs lösen jetzt InvalidOperationException aus</span><span class="sxs-lookup"><span data-stu-id="255ab-101">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="255ab-102">Einige mit <xref:System.Windows.Forms.DataGridView> verbundene APIs lösen jetzt eine <xref:System.InvalidOperationException>-Klasse aus, wenn der Wert der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType>-Eigenschaft `null` ist.</span><span class="sxs-lookup"><span data-stu-id="255ab-102">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="255ab-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="255ab-103">Change description</span></span>

<span data-ttu-id="255ab-104">In früheren .NET-Versionen lösen die betroffenen APIs eine <xref:System.NullReferenceException>-Klasse aus, wenn sie aufgerufen werden und der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner>-Wert `null` ist.</span><span class="sxs-lookup"><span data-stu-id="255ab-104">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="255ab-105">Ab .NET 5.0 lösen diese APIs anstelle einer <xref:System.NullReferenceException>-Klasse eine <xref:System.InvalidOperationException>-Klasse aus, wenn der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner>-Wert beim Aufruf `null` ist.</span><span class="sxs-lookup"><span data-stu-id="255ab-105">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="255ab-106">Das Auslösen einer <xref:System.InvalidOperationException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="255ab-106">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="255ab-107">Außerdem wird die Debugfunktion verbessert, indem deutlich auf die ungültige Eigenschaft hingewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="255ab-107">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="255ab-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="255ab-108">Version introduced</span></span>

<span data-ttu-id="255ab-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="255ab-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="255ab-110">Recommended action</span></span>

<span data-ttu-id="255ab-111">Überprüfen Sie den Code, und aktualisieren Sie ihn bei Bedarf, um zu verhindern, dass die betroffenen Typen mit der <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner>-Eigenschaft als `null` konstruiert werden.</span><span class="sxs-lookup"><span data-stu-id="255ab-111">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="255ab-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="255ab-112">Category</span></span>

<span data-ttu-id="255ab-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="255ab-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="255ab-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="255ab-114">Affected APIs</span></span>

<span data-ttu-id="255ab-115">In der folgenden Tabelle sind die betroffenen Eigenschaften und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="255ab-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="255ab-116">Betroffene Methode oder Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="255ab-116">Affected method or property</span></span> | <span data-ttu-id="255ab-117">Überprüfte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="255ab-117">Validated property</span></span> | <span data-ttu-id="255ab-118">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="255ab-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-119">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-120">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-121">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-122">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-123">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-124">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-125">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-126">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-127">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-128">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-129">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="255ab-130">5.0</span><span class="sxs-lookup"><span data-stu-id="255ab-130">5.0</span></span> |

<!-- 

#### Affected APIs

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

-->
